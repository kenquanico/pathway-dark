<script setup>
import { useReveal } from '../composables/useReveal'

const { el } = useReveal()
</script>

<template>
  <section ref="el" class="logo-strip reveal" aria-label="Trusted companies">
    <p>Trusted by the world's most innovative teams</p>
    <img src="/assets/logo-strip.svg" alt="Acme Corp, Quantum, Echo Valley, Celestial, Pulse, and Apex logos" />
  </section>
</template>

<style scoped>
.logo-strip {
  padding: 28px 20px 82px;
  background: #0a0008;
  text-align: center;
}

p {
  margin: 0;
  color: rgba(156, 163, 175, 0.5);
  font-size: 11px;
  font-weight: 600;
}

img {
  width: min(1024px, 90vw);
  margin: 30px auto 0;
  opacity: 0.36;
  filter: grayscale(1);
  transition: opacity 180ms ease;
}

img:hover {
  opacity: 0.62;
}
</style>
