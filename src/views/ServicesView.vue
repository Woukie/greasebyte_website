<script setup lang="ts">
import MorphingText from '@/components/MorphingText.vue'
</script>

<template>
  <div>
    <MorphingText
      :text="[
        'Critical infastructure',
        'Experience development',
        'menjanjikan tapi juga potensial bermasalah',
      ]"
    /><span> ■</span>
    <br />
    <MorphingText
      :text="[
        'Innovation in individuality',
        'Research and development',
        'Improve the quality of life',
      ]"
    /><span> ■</span>
    <br />
    <MorphingText
      :text="[
        'Eco friendly design',
        'Moderation in counter-terrorism',
        'Diversity in nieche markets',
      ]"
    /><span> ■</span>
    <br />
  </div>
</template>
