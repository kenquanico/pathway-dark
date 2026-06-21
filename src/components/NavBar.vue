<script setup>
import { onMounted, onUnmounted, ref } from 'vue'

const scrolled = ref(false)

function onScroll() {
  scrolled.value = window.scrollY > 8
}

onMounted(() => {
  onScroll()
  window.addEventListener('scroll', onScroll, { passive: true })
})

onUnmounted(() => {
  window.removeEventListener('scroll', onScroll)
})
</script>

<template>
  <header class="nav-bar" :class="{ scrolled }">
    <a class="brand" href="#" aria-label="Made by Framer">
      <img src="/assets/logo-default.svg" alt="" />
      <span>made by</span>
      <strong>Framer</strong>
    </a>

    <a class="nav-cta" href="#access">Get for free</a>
  </header>
</template>

<style scoped>
.nav-bar {
  position: fixed;
  inset: 36px 0 auto;
  z-index: 50;
  height: 56px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 clamp(16px, 4vw, 32px);
  background: rgba(10, 0, 8, 0.85);
  border-bottom: 1px solid rgba(255, 255, 255, 0.04);
  backdrop-filter: blur(14px);
  transition: background 180ms ease, border-color 180ms ease, backdrop-filter 180ms ease;
}

.nav-bar.scrolled {
  background: rgba(10, 0, 8, 0.94);
  border-bottom-color: var(--border);
  backdrop-filter: blur(20px);
}

.brand {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  color: rgba(255, 255, 255, 0.72);
  font-size: 12px;
  font-weight: 500;
  text-decoration: none;
}

.brand img {
  width: 30px;
  height: 30px;
}

.brand strong {
  color: #fff;
  font-weight: 800;
}

.nav-cta {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 36px;
  padding: 0 20px;
  border-radius: 999px;
  background: #fff;
  color: #0a0008;
  font-size: 12px;
  font-weight: 800;
  text-decoration: none;
  transition: transform 180ms ease, background 180ms ease;
}

.nav-cta:hover {
  background: rgba(255, 255, 255, 0.9);
  transform: translateY(-1px);
}
</style>
