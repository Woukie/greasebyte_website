<script setup lang="ts">
import MorphingText from '@/components/MorphingText.vue'
</script>

<template>
  <div>
    <div class="main-fade"></div>
    <p>About</p>
    <p>We're pioneering the search for a digital utopia<br />Help us find it...</p>

    <!-- Mad libs -->
    <div class="code">
      <span class="code-comment">
        <MorphingText
          :text="[
            'sell',
            'burn',
            'destroy',
            'hoard',
            'protect',
            'save',
            'evaluate',
            'consume',
            'trade',
            'consult',
            'beat',
            'deep fry',
            'wash',
            'donate',
            'recycle',
            'repair',
            'fake',
            'optimize',
            'analyze',
            'exchange',
          ]"
        />
        your
        <MorphingText
          :text="[
            'possessions',
            'mind',
            'csgo skins',
            'pokemon cards',
            'soul',
            'community',
            'body',
            'data',
            'privacy',
            'freedom',
            'girlfriend',
            'boyfriend',
            'dreams',
            'future',
            'social media accounts',
            'socks',
          ]"
        />
        for
        <MorphingText
          :text="[
            'free',
            'real guns',
            'more csgo skins',
            'profit',
            'fun',
            'a pickled egg',
            'power',
            'knowledge',
            'security',
            'love',
            'peace',
            'justice',
            'happiness',
            'divine purpose',
            'pride',
            'monopoly money',
            'more pokemon cards',
            'funkopops',
            'cancer',
            'dreams',
            'dreamSMP membership',
          ]"
        />
      </span>
      <br />
    </div>
  </div>
</template>
