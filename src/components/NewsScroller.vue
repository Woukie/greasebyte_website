<script setup lang="ts">
import { onMounted, ref } from 'vue'

const text = ['GREASEBYTE']

const speed = 0.2

const element = ref<HTMLElement | null>(null)

function sendText(element: HTMLElement) {
  const selectedText = text[Math.floor(Math.random() * text.length)]
  console.log(selectedText)

  if (!element) return

  const span = document.createElement('span')
  element.appendChild(span)
  span.innerText = selectedText
  span.style = 'position: absolute; white-space: pre;'

  const distance = span.offsetWidth + screen.width
  const keyframes = [
    { transform: 'translateX(0%)' },
    { transform: 'translateX(calc(-100vw - 100%))' },
  ]
  const timings = {
    duration: distance / speed,
    iterations: 1,
  }

  function cancelAnimation() {
    span.getAnimations().forEach((animation) => {
      animation.finish()
    })
  }

  window.addEventListener('resize', cancelAnimation)
  span.animate(keyframes, timings).addEventListener('finish', () => {
    window.removeEventListener('resize', cancelAnimation, false)
    span.remove()
    sendText(element)
  })
}

onMounted(() => {
  if (element.value) {
    sendText(element.value)
  }
})
</script>

<template>
  <div ref="element" class="news"></div>
</template>
