<template>
  <footer>
    <p>© 2024 Your Company Inc. All rights reserved</p>
    <div class="socials" aria-label="Social links">
      <a href="#" aria-label="X">X</a>
      <a href="#" aria-label="LinkedIn">in</a>
      <a href="#" aria-label="Instagram">
        <svg viewBox="0 0 24 24" aria-hidden="true">
          <rect x="5" y="5" width="14" height="14" rx="4" />
          <circle cx="12" cy="12" r="3" />
          <circle cx="16.5" cy="7.5" r="1" />
        </svg>
      </a>
      <a href="#" aria-label="TikTok">
        <svg viewBox="0 0 24 24" aria-hidden="true">
          <path d="M13 4v10.4a3.6 3.6 0 1 1-3-3.55" />
          <path d="M13 4c1.2 2.5 2.9 3.7 5 3.9" />
        </svg>
      </a>
      <a href="#" aria-label="YouTube">
        <svg viewBox="0 0 24 24" aria-hidden="true">
          <path d="M5 8.5c.2-1.4 1-2.2 2.4-2.35 3.1-.3 6.1-.3 9.2 0C18 6.3 18.8 7.1 19 8.5a24 24 0 0 1 0 7c-.2 1.4-1 2.2-2.4 2.35-3.1.3-6.1.3-9.2 0C6 17.7 5.2 16.9 5 15.5a24 24 0 0 1 0-7Z" />
          <path d="m10.5 9.5 4 2.5-4 2.5v-5Z" />
        </svg>
      </a>
    </div>
  </footer>
</template>

<style scoped>
footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
  padding: 24px clamp(20px, 4vw, 40px);
  border-top: 1px solid rgba(255, 255, 255, 0.06);
  background: #080610;
}

p {
  margin: 0;
  color: var(--text-subtle);
  font-size: 12px;
}

.socials {
  display: flex;
  align-items: center;
  gap: 16px;
}

a {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-width: 18px;
  color: var(--text-subtle);
  font-size: 13px;
  font-weight: 800;
  text-decoration: none;
  transition: color 180ms ease, transform 180ms ease;
}

a:hover {
  color: #fff;
  transform: translateY(-1px);
}

svg {
  width: 18px;
  height: 18px;
  fill: none;
  stroke: currentColor;
  stroke-width: 1.8;
  stroke-linecap: round;
  stroke-linejoin: round;
}

@media (max-width: 640px) {
  footer {
    flex-direction: column;
    text-align: center;
  }
}
</style>
