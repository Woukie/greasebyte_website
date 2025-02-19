<script setup lang="ts">
import { onMounted, ref } from 'vue'

const text = [
  `Hello? Hello, hello? Uh, I wanted to record a message for you to help you get settled in on your first night. Um, I actually worked in that office before you. I'm finishing up my last week now, as a matter of fact. So, I know it can be a bit overwhelming, but I'm here to tell you there's nothing to worry about. Uh, you'll do fine. So, let's just focus on getting you through your first week, okay?`,
  'At GreaseByte, work is more than a job – it’s a calling: To build. To design. To code. To consult. To think along with clients and sell. To make markets. To invent. To collaborate.',
  'GreaseByte’s mission is to empower every person and every organization on the planet to achieve more. As employees we come together with a growth mindset, innovate to empower others, and collaborate to realize our shared goals. Each day we build on our values of respect, integrity, and accountability to create a culture of inclusion where everyone can thrive at work and beyond.',
  `We have a unique culture that we are proud of. We think of ourselves primarily as problem-solvers, which itself is a two-part idea. We come up with the solution, but the solution isn't real until it is built and delivered to the customer. That penchant for action gives us a pragmatic approach to innovation, one that has served us well since 2025.`,
  `We care deeply about transforming lives with GreaseByte technology to enrich our industry, our communities, and the world. Our mission is to build great products that accelerate next-generation computing experiences – the building blocks for the data center, artificial intelligence, PCs, gaming and embedded. Underpinning our mission is the GreaseByte culture. We push the limits of innovation to solve the world’s most important challenges. We strive for execution excellence while being direct, humble, collaborative, and inclusive of diverse perspectives.`,
  `I saw Ryan Gosling at a grocery store in Los Angeles yesterday. I told him how cool it was to meet him in person, but I didn’t want to be a douche and bother him and ask him for photos or anything. He said, "Oh, like you’re doing now?" I was taken aback, and all I could say was "Huh?" but he kept cutting me off and going "huh? huh? huh?" and closing his hand shut in front of my face. I walked away and continued with my shopping, and I heard him chuckle as I walked off. When I came to pay for my stuff up front I saw him trying to walk out the doors with like fifteen Milky Ways in his hands without paying. The girl at the counter was very nice about it and professional, and was like "Sir, you need to pay for those first." At first he kept pretending to be tired and not hear her, but eventually turned back around and brought them to the counter. When she took one of the bars and started scanning it multiple times, he stopped her and told her to scan them each individually "to prevent any electrical infetterence," and then turned around and winked at me. I don’t even think that’s a word. After she scanned each bar and put them in a bag and started to say the price, he kept interrupting her by yawning really loudly.`
]

const speed = 0.3

const element = ref<HTMLElement | null>(null)

function sendText(element: HTMLElement, startMiddle: boolean) {
  const selectedText = text[Math.floor(Math.random() * text.length)]

  if (!element) return

  const span = document.createElement('span')
  span.innerText = selectedText
  span.style.position = 'absolute'
  span.style.whiteSpace = 'pre'
  element.appendChild(span)

  const endPosition = span.offsetWidth + element.offsetWidth
  let startPosition = 0

  if (startMiddle) {
    startPosition = endPosition * 0.5
  }

  const distance = endPosition - startPosition
  console.log(distance / speed)

  const timings = { duration: distance / speed, iterations: 1 }
  const keyframes = [
    { transform: 'translateX(-'+ startPosition +'px'},
    { transform: 'translateX(-'+ endPosition +'px)' },
  ]

  function cancelAnimation() {
    span.getAnimations().forEach((animation) => {
      animation.finish()
    })
  }

  window.addEventListener('resize', cancelAnimation)
  span.animate(keyframes, timings).addEventListener('finish', () => {
    window.removeEventListener('resize', cancelAnimation, false)
    span.remove()
    sendText(element, false)
  })
}

onMounted(() => {
  if (element.value) {
    sendText(element.value, true)
  }
})
</script>

<template>
  <div ref="element" class="news"></div>
</template>
