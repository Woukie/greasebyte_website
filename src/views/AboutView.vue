<script setup lang="ts">
import MorphingText from '@/components/MorphingText.vue'
</script>

<template>
  <div>
    <div class="main-fade"></div>
    <p>About</p>
    <p>We're making special games for special people<br />...</p>

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
            'rent out',
            'consult',
            'beat',
            'deep fry',
            'wash',
            'donate',
            'morgage',
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
            'discord account',
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
            'nothing',
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
