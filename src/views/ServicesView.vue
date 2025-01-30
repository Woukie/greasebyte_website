<script setup lang="ts">
import MorphingText from '@/components/MorphingText.vue'
</script>

<template>
  <div>
    <div class="main-fade"></div>
    <p>Services</p>
    <div class="code">
      <span class="code-comment">We specialize in three areas<br /></span>
    </div>

    <MorphingText
      :text="[
        'Critical infastructure',
        'Server hosting',
        'menjanjikan tapi juga potensial bermasalah',
        'Critical infrastructure',
        'Cloud computing',
        'Artificial Intelligence',
        'Cybersecurity',
        'Blockchain technology',
        'Data analytics',
        'Internet of Things (IoT)',
        'Machine learning',
      ]"
    /><span>─┤</span>
    <br />
    <MorphingText
      :text="[
        'Consultancy',
        'Advertising',
        'Human resources management',
        'Financial advisory',
        'Legal services',
        'Public relations',
        'Marketing',
        'Recruitment',
        'Training',
      ]"
    /><span>─┤</span>
    <br />
    <MorphingText
      :text="[
        'Environmentally sustainable design',
        'Moderation for counter-terrorism',
        'Sustainability in software',
        'Policy design',
        'Equal opportunities',
      ]"
    /><span>─┘</span>
  </div>
</template>
