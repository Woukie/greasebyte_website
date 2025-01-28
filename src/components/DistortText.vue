<script setup lang="ts">
import { defineProps } from 'vue'

defineProps({
  text: String,
})

function scramble(event: MouseEvent) {
  const element = event.target as HTMLElement
  if (!element.dataset.defaultText) {
    element.dataset.defaultText = element.innerText

    // Unscramble the text
    const interval = setInterval(() => {
      const innerText = element.innerText
      let text = ''
      for (let i = 0; i < innerText.length; i++) {
        if (Math.random() < 0.5) {
          text += element.dataset.defaultText?.charAt(i)
          continue
        }
        text += innerText.charAt(i)
      }
      element.innerText = text

      if (text === element.dataset.defaultText) {
        element.dataset.defaultText = ''
        clearInterval(interval)
      }
    }, 120)
  }

  const innerText = element.innerText
  let text = ''
  for (let i = 0; i < innerText.length; i++) {
    if (Math.random() < 0.1) {
      const start = 33
      const end = 126
      text += String.fromCharCode(Math.floor(Math.random() * (end - start + 1)) + start)
      continue
    }
    text += innerText.charAt(i)
  }
  element.innerText = text
}
</script>

<template>
  <span @mousemove="scramble">
    {{ text }}
  </span>
</template>
