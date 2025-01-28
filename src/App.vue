<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import DistortText from './components/DistortText.vue'
import MorphingText from './components/MorphingText.vue'
import NewsScroller from './components/NewsScroller.vue'
</script>

<template>
  <!-- <img alt="Red alert" src="https://www.heavensgate.com/img/redalrt3.gif" /> -->
  <header>
    <NewsScroller />
  </header>

  <div class="vignette"></div>

  <div class="container">
    <nav class="navigator">
      <div class="navigator-content">
        <!-- <p>greasebyte</p> -->
        <div class="code">
          <span>
            <span class="code-comment">// when compared with other retailers</span>
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
          https://greasebyte.net
          <br />
          ├─<RouterLink to="/"><DistortText text="/" /></RouterLink>
          <br />
          ├─<RouterLink to="/about"><DistortText text="/about" /></RouterLink>
          <br />
          └─<RouterLink to="/services"><DistortText text="/services" /></RouterLink>
        </div>
      </div>
    </nav>

    <main class="main">
      <div class="main-content">
        <router-view v-slot="{ Component }">
          <transition name="slide-fade" mode="out-in">
            <component :is="Component" />
          </transition>
        </router-view>
      </div>
    </main>
  </div>

  <!-- <footer>
    <p>© 2025 GreaseByte</p>
    <a href="https://int10h.org/oldschool-pc-fonts/fontlist/font?dos-v_re_jpn19"
      ><DistortText text="Font"
    /></a>
  </footer> -->
</template>

<style scoped></style>
