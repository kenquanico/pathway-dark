<script setup>
import { useReveal } from '../composables/useReveal'

const { el } = useReveal()
</script>

<template>
  <section id="access" ref="el" class="access reveal">
    <img class="floating floating-left" src="/assets/helix2-1.svg" alt="" />
    <img class="floating floating-right" src="/assets/emojistar-1.svg" alt="" />

    <div class="access-content">
      <h2>Get instant access</h2>
      <p>Celebrate the joy of accomplishment with an app designed to track your progress and motivate your efforts.</p>

      <form>
        <label class="sr-only" for="email">Email address</label>
        <input id="email" type="email" placeholder="name@email.com" />
        <button type="submit">Get access</button>
      </form>
    </div>
  </section>
</template>

<style scoped>
.access {
  position: relative;
  overflow: hidden;
  min-height: 430px;
  display: grid;
  place-items: center;
  padding: 92px 20px 105px;
  background: #0a0008;
}

.access-content {
  position: relative;
  z-index: 2;
  width: min(520px, 100%);
  text-align: center;
}

h2 {
  margin: 0;
  color: #fff;
  font-size: clamp(38px, 7vw, 58px);
  font-weight: 700;
  letter-spacing: 0;
  line-height: 1;
}

p {
  width: min(420px, 100%);
  margin: 22px auto 0;
  color: rgba(255, 255, 255, 0.52);
  font-size: 14px;
  font-weight: 500;
  line-height: 1.55;
}

form {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-top: 28px;
}

input,
button {
  min-height: 43px;
  border-radius: 8px;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

input {
  width: min(290px, 100%);
  padding: 0 16px;
  background: #3b3b3b;
  color: #fff;
  font-size: 14px;
  outline: none;
}

input::placeholder {
  color: rgba(255, 255, 255, 0.42);
}

input:focus {
  border-color: rgba(168, 85, 247, 0.72);
  box-shadow: 0 0 0 4px rgba(168, 85, 247, 0.16);
}

button {
  padding: 0 20px;
  background: #fff;
  color: #0a0008;
  font-size: 13px;
  font-weight: 800;
  transition: transform 180ms ease, background 180ms ease;
}

button:hover {
  background: rgba(255, 255, 255, 0.9);
  transform: translateY(-1px);
}

.floating {
  position: absolute;
  z-index: 1;
  pointer-events: none;
  filter: drop-shadow(0 28px 46px rgba(103, 58, 183, 0.38));
  animation: float 5s ease-in-out infinite;
}

.floating-left {
  --rotate: -18deg;
  left: clamp(-74px, 4vw, 54px);
  bottom: 70px;
  width: clamp(150px, 23vw, 280px);
}

.floating-right {
  --rotate: 14deg;
  right: clamp(-62px, 7vw, 86px);
  bottom: 84px;
  width: clamp(130px, 19vw, 230px);
  animation-duration: 4.2s;
  animation-direction: reverse;
}

.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}

@media (max-width: 640px) {
  .access {
    padding-bottom: 180px;
  }

  form {
    flex-direction: column;
    align-items: stretch;
  }

  input {
    width: 100%;
  }

  .floating-left {
    bottom: 18px;
    left: -54px;
  }

  .floating-right {
    right: -42px;
    bottom: 18px;
  }
}
</style>
