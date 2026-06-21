<script setup>
import AnnouncementBar from './components/AnnouncementBar.vue'
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import LogoStrip from './components/LogoStrip.vue'
import FeaturesSection from './components/FeaturesSection.vue'
import InterfaceSection from './components/InterfaceSection.vue'
import FaqSection from './components/FaqSection.vue'
import AccessSection from './components/AccessSection.vue'
import FooterSection from './components/FooterSection.vue'
</script>

<template>
  <AnnouncementBar />
  <NavBar />
  <main>
    <HeroSection />
    <LogoStrip />
    <FeaturesSection />
    <InterfaceSection />
    <FaqSection />
    <AccessSection />
  </main>
  <FooterSection />
</template>

<style>
:root {
  --bg-base: #0a0008;
  --bg-hero: radial-gradient(ellipse 80% 60% at 50% 0%, #3b0764 0%, #1a0033 40%, #0a0008 70%);
  --bg-surface: #130f1a;
  --bg-card: #1a1525;
  --border: rgba(255, 255, 255, 0.07);
  --accent: #a855f7;
  --accent-glow: rgba(168, 85, 247, 0.25);
  --text-primary: #ffffff;
  --text-muted: #9ca3af;
  --text-subtle: #6b7280;
  --radius-card: 14px;
  --font-ag: "AG", "Aktiv Grotesk", "Avenir Next", "Helvetica Neue", Arial, sans-serif;
}

* {
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  min-width: 320px;
  background: var(--bg-base);
  color: var(--text-primary);
  font-family: var(--font-ag);
  font-synthesis: none;
  overflow-x: hidden;
}

button,
input {
  font: inherit;
}

button {
  cursor: pointer;
}

img {
  display: block;
  max-width: 100%;
}

#app {
  min-height: 100vh;
  background: var(--bg-base);
}

.reveal {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 600ms ease-out, transform 600ms ease-out;
}

.reveal.is-visible {
  opacity: 1;
  transform: translateY(0);
}

@keyframes float {
  0%,
  100% {
    transform: translate3d(0, 0, 0) rotate(var(--rotate, 0deg));
  }

  50% {
    transform: translate3d(0, -16px, 0) rotate(var(--rotate, 0deg));
  }
}

@keyframes slow-spin {
  to {
    transform: rotate(360deg);
  }
}
</style>
