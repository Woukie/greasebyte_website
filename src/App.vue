<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import DistortText from './components/DistortText.vue'
import MorphingText from './components/MorphingText.vue'
import NewsScroller from './components/NewsScroller.vue'
</script>

<template>
  <header>
    <NewsScroller />
  </header>

  <div class="vignette"></div>

  <div class="container">
    <main class="main">
      <div class="main-content">
        <router-view v-slot="{ Component }">
          <transition name="slide-fade" mode="out-in">
            <component :is="Component" />
          </transition>
        </router-view>
      </div>
    </main>

    <nav class="navigator" style="pointer-events: none">
      <div class="navigator-content">
        <div class="code navigator-fade">
          <span>
            <span class="code-comment">// when compared with other developers</span>
            <br />
            <span>
              <MorphingText
                :text="[
                  'creativity',
                  'innovation',
                  'motivation',
                  'style',
                  'profit',
                  'expertise',
                  'quality',
                  'security',
                  'speed',
                  'reliability',
                  'efficiency',
                  'sustainability',
                  'flexibility',
                  'responsibility',
                  'trust',
                  'experience',
                ]"
              />
              *= 1.32;
            </span>
          </span>
        </div>
        <br />
        <div>
          <span>https://greasebyte.net</span>
          <br />
          ├─<RouterLink to="/" style="pointer-events: all"><DistortText text="/" /></RouterLink>
          <br />
          ├─<RouterLink to="/about" style="pointer-events: all"
            ><DistortText text="/about"
          /></RouterLink>
          <br />
          └─<RouterLink to="/services" style="pointer-events: all"
            ><DistortText text="/services"
          /></RouterLink>
        </div>
      </div>
    </nav>
  </div>

  <footer>
    <NewsScroller style="bottom: 0" />
  </footer>
</template>

<style scoped></style>
