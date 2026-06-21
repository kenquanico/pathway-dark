<script setup>
import { ref } from 'vue'
import { useReveal } from '../composables/useReveal'

const { el } = useReveal()
const open = ref([false, false, false, false])

function toggle(index) {
  open.value[index] = !open.value[index]
}
</script>

<template>
  <section ref="el" class="faq reveal">
    <h2>Frequently asked questions</h2>

    <div class="accordion">
      <div v-for="(_, index) in open" :key="index" class="faq-item">
        <button type="button" :aria-expanded="open[index]" @click="toggle(index)">
          <span>How does the pricing work for teams</span>
          <strong>{{ open[index] ? '−' : '+' }}</strong>
        </button>
        <div class="answer" :class="{ open: open[index] }">
          <p>
            Our pricing is based on the number of seats in your workspace. Each seat covers one team member with full
            access to all features.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.faq {
  padding: 116px 20px 150px;
  background: linear-gradient(to bottom, #5826a4 0%, #4f2292 18%, #271242 66%, #0a0008 100%);
}

h2 {
  margin: 0;
  color: #fff;
  font-size: clamp(34px, 6vw, 52px);
  font-weight: 700;
  letter-spacing: 0;
  line-height: 1;
  text-align: center;
}

.accordion {
  width: min(680px, 100%);
  margin: 70px auto 0;
}

.faq-item {
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

button {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  border: 0;
  padding: 22px 0;
  background: transparent;
  color: #fff;
  font-size: 15px;
  font-weight: 700;
  text-align: left;
}

strong {
  color: rgba(255, 255, 255, 0.7);
  font-size: 26px;
  font-weight: 400;
  line-height: 1;
}

.answer {
  max-height: 0;
  overflow: hidden;
  transition: max-height 240ms ease;
}

.answer.open {
  max-height: 120px;
}

p {
  margin: 0;
  padding: 0 48px 22px 0;
  color: rgba(255, 255, 255, 0.66);
  font-size: 14px;
  line-height: 1.55;
}
</style>
