<script setup lang="ts">
import MorphingText from '@/components/MorphingText.vue'
</script>

<template>
  <div>
    <div class="main-fade"></div>
    <p>Services</p>
    <div class="code">
      <span class="code-comment">We specialize in three specific areas<br /></span>
    </div>

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
    /><span> ╣</span>
    <br />
    <MorphingText
      :text="[
        'Consultancy',
        'Advertising',
        'Data analytics',
        'Human resources management',
        'Financial advisory',
      ]"
    /><span> ╣</span>
    <br />
    <MorphingText
      :text="[
        'Environmentally sustainable design',
        'Moderation for counter-terrorism',
        'Sustainability in software',
        'Policy design',
        'Equal opportunities',
      ]"
    /><span> ╝</span>
  </div>
</template>
