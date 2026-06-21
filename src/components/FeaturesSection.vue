<script setup>
import { useReveal } from '../composables/useReveal'

const { el } = useReveal()

const features = [
  {
    title: 'Integration ecosystem',
    description: 'Enhance your productivity by connecting with your favorite tools, keeping all your essentials in one place.',
    icon: 'link',
  },
  {
    title: 'Goal setting and tracking',
    description: 'Define and track your goals, breaking down objectives into achievable tasks to keep your targets in sight.',
    icon: 'target',
  },
  {
    title: 'Secure data encryption',
    description: 'With end-to-end encryption, your data is securely stored and protected from unauthorized access.',
    icon: 'lock',
  },
]
</script>

<template>
  <section ref="el" class="features reveal">
    <div class="section-heading">
      <h2>Everything you need</h2>
      <p>
        Enjoy customizable lists, team work tools, and smart tracking all in one place. Set tasks, get reminders, and
        see your progress simply and quickly.
      </p>
    </div>

    <div class="feature-grid">
      <article v-for="feature in features" :key="feature.title" class="feature-card">
        <div class="icon-box">
          <svg v-if="feature.icon === 'link'" viewBox="0 0 24 24" aria-hidden="true">
            <path d="M10.5 13.5 13.5 10.5" />
            <path d="M8.2 15.8a3 3 0 0 1 0-4.2l1.4-1.4" />
            <path d="M15.8 8.2a3 3 0 0 1 0 4.2l-1.4 1.4" />
          </svg>
          <svg v-else-if="feature.icon === 'target'" viewBox="0 0 24 24" aria-hidden="true">
            <circle cx="12" cy="12" r="7" />
            <circle cx="12" cy="12" r="3" />
          </svg>
          <svg v-else viewBox="0 0 24 24" aria-hidden="true">
            <rect x="6" y="10" width="12" height="9" rx="2" />
            <path d="M9 10V8a3 3 0 0 1 6 0v2" />
          </svg>
        </div>
        <h3>{{ feature.title }}</h3>
        <p>{{ feature.description }}</p>
      </article>
    </div>
  </section>
</template>

<style scoped>
.features {
  padding: 82px 20px 132px;
  background: #0a0008;
}

.section-heading {
  width: min(560px, 100%);
  margin: 0 auto;
  text-align: center;
}

h2 {
  margin: 0;
  color: #fff;
  font-size: clamp(34px, 6vw, 52px);
  font-weight: 700;
  letter-spacing: 0;
  line-height: 1;
}

.section-heading p {
  margin: 22px auto 0;
  color: rgba(255, 255, 255, 0.68);
  font-size: 17px;
  font-weight: 500;
  line-height: 1.5;
}

.feature-grid {
  width: min(1120px, 100%);
  margin: 66px auto 0;
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 16px;
}

.feature-card {
  min-height: 260px;
  padding: 38px 28px 34px;
  border: 1px solid var(--border);
  border-radius: var(--radius-card);
  background: #101010;
  text-align: center;
  box-shadow: inset 0 1px rgba(255, 255, 255, 0.03);
}

.icon-box {
  width: 54px;
  height: 54px;
  display: grid;
  place-items: center;
  margin: 0 auto 27px;
  border-radius: 10px;
  background: #fff;
  color: #17131f;
}

svg {
  width: 22px;
  height: 22px;
  fill: none;
  stroke: currentColor;
  stroke-width: 2;
  stroke-linecap: round;
  stroke-linejoin: round;
}

h3 {
  margin: 0;
  color: #fff;
  font-size: 14px;
  font-weight: 800;
}

.feature-card p {
  margin: 12px 0 0;
  color: rgba(255, 255, 255, 0.66);
  font-size: 13px;
  line-height: 1.52;
}

@media (max-width: 820px) {
  .feature-grid {
    grid-template-columns: 1fr;
    max-width: 520px;
  }
}
</style>
