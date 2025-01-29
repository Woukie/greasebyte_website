<script setup lang="ts">
import { defineProps, onMounted, onUnmounted, ref } from 'vue'

const element = ref<HTMLElement | null>(null)

const props = defineProps<{
  text: string[]
}>()

function morph(element: HTMLElement) {
  if (element.dataset.busy === undefined) {
    element.dataset.busy = 'false'
  }

  const busy = element.dataset.busy === 'true'

  if (busy) {
    return
  }

  const nextIndex = Math.floor(Math.random() * props.text.length)
  element.dataset.busy = 'true'

  let text = ''
  for (let i = 0; i < props.text[nextIndex].length; i++) {
    const start = 33
    const end = 126
    text += String.fromCharCode(Math.floor(Math.random() * (end - start + 1)) + start)
  }
  element.innerText = text

  const unscrambleInterval = setInterval(() => {
    const innerText = element.innerText
    let text = ''
    const longest = Math.max(innerText.length, props.text[nextIndex].length)
    for (let i = 0; i < longest; i++) {
      if (Math.random() < 0.4) {
        text += props.text[nextIndex].charAt(i) || ''
        continue
      }
      text += innerText.charAt(i) || ''
    }
    element.innerText = text

    if (text === props.text[nextIndex]) {
      element.dataset.busy = 'false'
      clearInterval(unscrambleInterval)
    }
  }, 100)
}

let interval: number | undefined

onMounted(() => {
  interval = setInterval(() => {
    if (element.value && Math.random() < 0.01) {
      morph(element.value)
    }
  }, 100)
})

onUnmounted(() => {
  clearInterval(interval)
})
</script>

<template>
  <span ref="element">
    {{ text[0] }}
  </span>
</template>
