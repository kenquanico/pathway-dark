<script setup>
import { useReveal } from '../composables/useReveal'

const { el } = useReveal()
</script>

<template>
  <section ref="el" class="hero reveal">
    <div class="hero-glow" aria-hidden="true"></div>
    <img class="hero-shape hero-shape-left" src="/assets/cursor-2.svg" alt="" />
    <img class="hero-shape hero-shape-right" src="/assets/message-1.svg" alt="" />

    <div class="hero-content">
      <div class="badge">
        <span>Version 2.0 is here</span>
        <a href="#">Read more →</a>
      </div>

      <h1>
        <span>One Task</span>
        <span>at a Time</span>
      </h1>

      <p>
        Celebrate the joy of accomplishment with an app designed to track your progress, motivate your efforts, and
        celebrate your successes.
      </p>

      <a class="hero-cta" href="#access">Get for free</a>
    </div>

    <div class="hero-curve" aria-hidden="true"></div>
  </section>
</template>

<style scoped>
.hero {
  position: relative;
  min-height: 100vh;
  display: grid;
  place-items: center;
  overflow: hidden;
  padding: 170px 20px 130px;
  background:
    radial-gradient(ellipse 100% 70% at 50% -10%, #5b21b6 0%, #3b0764 30%, #1a0033 55%, #0a0008 80%),
    var(--bg-base);
}

.hero::after {
  content: "";
  position: absolute;
  left: 50%;
  bottom: -175px;
  width: min(1180px, 120vw);
  height: 330px;
  transform: translateX(-50%);
  border-radius: 50% 50% 0 0;
  background: radial-gradient(ellipse at center, rgba(170, 93, 255, 0.8), rgba(10, 0, 8, 0.95) 66%);
  box-shadow: 0 -36px 70px rgba(168, 85, 247, 0.45), inset 0 28px 35px rgba(255, 255, 255, 0.12);
  opacity: 0.95;
}

.hero-glow {
  position: absolute;
  top: -140px;
  left: 50%;
  width: 640px;
  height: 640px;
  transform: translateX(-50%);
  border-radius: 50%;
  background: radial-gradient(circle, rgba(168, 85, 247, 0.42), transparent 68%);
  filter: blur(80px);
  opacity: 0.72;
}

.hero-content {
  position: relative;
  z-index: 2;
  width: min(900px, 100%);
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 7px 13px;
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 999px;
  background: rgba(255, 255, 255, 0.06);
  color: rgba(255, 255, 255, 0.62);
  font-size: 11px;
  font-weight: 600;
  box-shadow: inset 0 1px rgba(255, 255, 255, 0.08);
}

.badge a {
  color: #d8b4fe;
  text-decoration: none;
}

h1 {
  margin: 34px 0 0;
  color: #fff;
  font-size: clamp(62px, 12vw, 138px);
  font-weight: 700;
  letter-spacing: 0;
  line-height: 0.9;
}

h1 span {
  display: block;
}

p {
  width: min(420px, 100%);
  margin: 32px auto 0;
  color: rgba(255, 255, 255, 0.72);
  font-size: clamp(15px, 2vw, 17px);
  font-weight: 500;
  line-height: 1.45;
}

.hero-cta {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 48px;
  margin-top: 28px;
  padding: 0 28px;
  border-radius: 12px;
  background: #fff;
  color: #0a0008;
  font-size: 13px;
  font-weight: 800;
  text-decoration: none;
  transition: transform 180ms ease, background 180ms ease;
}

.hero-cta:hover {
  background: rgba(255, 255, 255, 0.9);
  transform: translateY(-2px);
}

.hero-shape {
  position: absolute;
  z-index: 3;
  pointer-events: none;
  filter: drop-shadow(0 24px 42px rgba(92, 32, 206, 0.46));
  animation: float 4s ease-in-out infinite;
}

.hero-shape-left {
  --rotate: -8deg;
  top: 36%;
  left: max(5vw, calc(50% - 520px));
  width: clamp(128px, 20vw, 220px);
}

.hero-shape-right {
  --rotate: 6deg;
  top: 30%;
  right: max(5vw, calc(50% - 520px));
  width: clamp(128px, 18vw, 220px);
  animation-duration: 4.8s;
  animation-direction: reverse;
}

.hero-curve {
  position: absolute;
  inset: auto 0 0;
  z-index: 4;
  height: 140px;
  background: linear-gradient(to bottom, transparent, #0a0008);
  pointer-events: none;
}

@media (max-width: 760px) {
  .hero {
    padding-top: 142px;
  }

  .hero-shape-left {
    top: 31%;
    left: -22px;
  }

  .hero-shape-right {
    top: 28%;
    right: -20px;
  }
}
</style>
