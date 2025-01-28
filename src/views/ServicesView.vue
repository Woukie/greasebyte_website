<script setup lang="ts">
import MorphingText from '@/components/MorphingText.vue'
</script>

<template>
  <div>
    <span>Services<br />We specialise in four main categories</span>
    <p></p>
    <MorphingText
      :text="[
        'Critical infastructure',
        'Server hosting',
        'menjanjikan tapi juga potensial bermasalah',
        'Critical infrastructure',
        'Server hosting',
        'Cloud computing',
        'Artificial Intelligence',
        'Cybersecurity',
        'Blockchain technology',
        'Data analytics',
        'Internet of Things (IoT)',
        'Server hosting',
        'Machine learning',
        'Quantum computing',
      ]"
    /><span> ■</span>
    <br />
    <MorphingText
      :text="[
        'Innovation',
        'Research and development',
        'Software Prototyping',
        'Software Design',
        'Virtual reality',
        'Augmented reality',
      ]"
    /><span> ■</span>
    <br />
    <MorphingText
      :text="[
        'Consultancy',
        'Advertising',
        'Data analytics',
        'Human resources management',
        'Financial advisory',
      ]"
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
  </div>
</template>
