<script setup lang="ts">
import MorphingText from '@/components/MorphingText.vue'
</script>

<template>
  <div>
    <MorphingText
      :text="[
        'Critical infastructure',
        'Server hosting',
        'menjanjikan tapi juga potensial bermasalah',
      ]"
    /><span> ■</span>
    <br />
    <MorphingText :text="['Innovation', 'Research and development']" /><span> ■</span>
    <br />
    <MorphingText
      :text="[
        'Eco friendly design',
        'Moderation in counter-terrorism',
        'Experience design',
        'Web design',
      ]"
    /><span> ■</span>
    <br />
    <MorphingText :text="['Consultancy', 'Cooking', 'Advertising']" /><span> ■</span>
  </div>
</template>
