<script setup lang="ts">
import MorphingText from '@/components/MorphingText.vue'
</script>

<template>
  <div>
    <span>Services<br />We specialise in four main categories</span>
    <MorphingText
      :text="[
        'Critical infastructure',
        'Server hosting',
        'Software development',
        'menjanjikan tapi juga potensial bermasalah',
      ]"
    /><span> ■</span>
    <br />
    <MorphingText
      :text="['Innovation', 'Research and development', 'Software Prototyping', 'Software Design']"
    /><span> ■</span>
    <br />
    <MorphingText
      :text="[
        'Environmentally sustainable design',
        'Moderation for counter-terrorism',
        'Sustainability in software',
        'Policy design',
        'Equal opportunities',
      ]"
    /><span> ■</span>
    <br />
    <MorphingText :text="['Consultancy', 'Cooking', 'Advertising']" /><span> ■</span>
  </div>
</template>
