<template>
  <div class="announcement-bar">
    <p>This page is included in a free SaaS Website Kit. View the complete Kit <span>→</span></p>
  </div>
</template>

<style scoped>
.announcement-bar {
  position: fixed;
  inset: 0 0 auto;
  z-index: 60;
  height: 36px;
  display: grid;
  place-items: center;
  padding: 0 16px;
  background: linear-gradient(90deg, #feccff 0%, #fff4d6 48%, #c3efff 100%);
  border-bottom: 1px solid var(--border);
}

p {
  margin: 0;
  color: rgba(10, 0, 8, 0.78);
  font-size: 11px;
  font-weight: 700;
  line-height: 1.2;
  text-align: center;
}

span {
  color: #111827;
}
</style>
