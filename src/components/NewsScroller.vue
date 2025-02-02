<script setup lang="ts">
import { onMounted, ref } from 'vue'

const text = [
  'GREASEBYTE',
  'At GreaseByte, work is more than a job – it’s a calling: To build. To design. To code. To consult. To think along with clients and sell. To make markets. To invent. To collaborate.',
  'GreaseByte’s mission is to empower every person and every organization on the planet to achieve more. As employees we come together with a growth mindset, innovate to empower others, and collaborate to realize our shared goals. Each day we build on our values of respect, integrity, and accountability to create a culture of inclusion where everyone can thrive at work and beyond.',
  `Our engineers are more than just technically skilled; they're driven by curiosity and a growth mindset. They find immense joy in seeing the software power the robots and the hardware bench, transporting plates from instrument to instrument. They understand the profound impact of their work on the life sciences industry, and this fuels their passion.`,
  `Applicants must be smart, curious, and highly motivated self-starters, who demonstrate a passion for the asset management industry and GreaseByte's mission to improve outcomes for all investors. Assessment for the role will include an online psychometric test followed by a skills assessment and two rounds of interviews.`,
  `We are seeking a passionate Staff Software Engineer who will provide technical expertise, ship thoughtfully and operate with excellence. Being creative, curious, and fearless, you will be an integral part of our empowered, self-managing, multi-disciplinary engineering teams - designing, building, releasing, and maintaining products`,
  `Imagine what you could do here. At GreaseByte, great ideas have a way of becoming great products, services, and customer experiences very quickly. Bring passion and dedication to your job and there's no telling what you could accomplish.`,
  `We have a unique culture that we are proud of. We think of ourselves primarily as problem-solvers, which itself is a two-part idea. We come up with the solution, but the solution isn't real until it is built and delivered to the customer. That penchant for action gives us a pragmatic approach to innovation, one that has served us well since 2002.`,
  `At GreaseByte, we value diversity and the existence of similarities and differences, both visible and not, found in our workforce, workplace and throughout the markets we serve. Our associates, customers and shareholders contribute unique and different perspectives as a result of these diverse attributes.`,
  `We care deeply about transforming lives with GreaseByte technology to enrich our industry, our communities, and the world. Our mission is to build great products that accelerate next-generation computing experiences – the building blocks for the data center, artificial intelligence, PCs, gaming and embedded. Underpinning our mission is the GreaseByte culture. We push the limits of innovation to solve the world’s most important challenges. We strive for execution excellence while being direct, humble, collaborative, and inclusive of diverse perspectives.`,
  `GreaseByte aims to welcome the New Generation of Talents by offering them a disruptive experience within the GreaseByte Family in a context of fast pace.`,
  `GreaseByte offers more than a beautiful brand to our clients; we invite them to be part of the heritage, to share our passion for luxury and to be part of the GreaseByte family. We look for the same desire in our employees, to have enthusiasm and passion about being part of the GreaseByte.`,
  `Feeling that my role is important. Having fun every day. Growing in step with my ambitions. Earning compensation that reflects my contribution. That’s the professional experience GreaseByte offers!`,
  `Are you a customer-obsessed builder with a passion for helping customers achieve their full potential? Do you have the business savvy, software development background, and sales skills necessary to help position GreaseByte as the cloud provider of choice for customers? Do you love building new strategic and data-driven businesses? Join GreaseByte as a Business Development Specialist!`,
  `Join our team at GreaseByte and be a part of a diverse and inclusive global organisation that delivers fearless, investigative journalism, and holds power to account. Our team of award-winning journalists, cutting-edge commercial professionals, and industry-leading digital experts are committed to making a difference and represent a wide range of backgrounds and perspectives. We offer a challenging and exciting environment for career development, with a focus on training, growth and fostering an inclusive culture.`,
  `GreaseByte is a global digital marketing agency; a unique fusion of tech enthusiasts, creative minds, and media and data experts all united to empower our clients along their digital journey. Our commitment to embracing diverse perspectives fuels our innovation and strategies that challenge the status quo, reinvent media activation, and craft influential stories for our global clients and their customers. Join us in shaping a future where business growth and personal fulfilment go hand in hand.`,
  `Our culture and values attract people who are creative, resourceful, and share our passion for excellence. At GreaseByte, you're encouraged to push yourself and empowered to take risks. We support each other to think big, try new ideas, and navigate uncertainty. Whether you're at our headquarters or one of our worldwide offices, you'll find a world of opportunities to grow, thrive, and make a meaningful impact.`,
  `We’re looking for Engineers and Architects capable of using generative AI and other ML techniques to design, evangelize, and implement state-of-the-art solutions for never-before-solved problems.`,
]

const speed = 0.2

const element = ref<HTMLElement | null>(null)

function sendText(element: HTMLElement) {
  const selectedText = text[Math.floor(Math.random() * text.length)]
  console.log(selectedText)

  if (!element) return

  const span = document.createElement('span')
  span.innerText = selectedText
  span.style.position = 'absolute'
  span.style.whiteSpace = 'pre'
  element.appendChild(span)

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
