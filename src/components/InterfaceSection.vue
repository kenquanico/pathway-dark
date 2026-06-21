<script setup>
import { useReveal } from '../composables/useReveal'

const { el } = useReveal()

const taskGroups = [
  {
    label: 'Design',
    tasks: [
      ['Define color scheme & typography', 'Mar 21', 'Done', true],
      ['Design homepage', 'Apr 10', 'Done', true],
      ['Design responsive layouts for mobile and tablet views', 'Apr 15', 'In progress', false],
      ['Implement navigation with dropdowns', 'Apr 18', 'In progress', false],
      ['Add animations', 'Apr 22', 'Done', false],
    ],
  },
  {
    label: 'SEO',
    tasks: [
      ['Research and integrate relevant keywords', 'Mar 21', 'In progress', false],
      ['Ensure all pages have meta titles and descriptions', 'Apr 12', 'In progress', false],
      ['Set up Google Analytics', 'Mar 26', 'Done', true],
    ],
  },
  {
    label: 'Testing',
    tasks: [
      ['Conduct usability testing with a small group of users', 'Apr 28', 'In progress', false],
      ['Test on different devices and browsers for compatibility', 'Apr 30', 'In progress', false],
    ],
  },
]

const navItems = ['Website', 'Holiday Campaign', 'SEO', 'Collaborations', 'Product', 'Analytics', 'Finances']
</script>

<template>
  <section ref="el" class="interface reveal">
    <div class="section-heading">
      <h2>Intuitive interface</h2>
      <p>
        Celebrate the joy of accomplishment with an app designed to track your progress, motivate your efforts, and
        celebrate your successes, one task at a time.
      </p>
    </div>

    <div class="mockup-wrap">
      <div class="window-bar">
        <div class="dots" aria-hidden="true">
          <span></span>
          <span></span>
          <span></span>
        </div>
        <div class="search">Search</div>
      </div>

      <div class="mockup-body">
        <aside>
          <div class="workspace">▣ <strong>Marketing</strong></div>
          <nav>
            <a v-for="(item, index) in navItems" :key="item" :class="{ active: index === 0, divider: index === 4 }">
              <span>{{ ['▤', '◴', '⌕', '◎', '✧', '▰', '$'][index] }}</span>
              {{ item }}
            </a>
          </nav>
          <div class="avatar"></div>
        </aside>

        <div class="content">
          <div class="breadcrumb">Marketing / Website</div>
          <div class="title-row">
            <h3>Launch</h3>
            <div>☰ ⠿</div>
          </div>

          <div v-for="group in taskGroups" :key="group.label" class="task-group">
            <div class="group-label">{{ group.label }}</div>
            <div v-for="task in group.tasks" :key="task[0]" class="task-row">
              <div class="task-name">
                <span class="check" :class="{ done: task[3] }">{{ task[3] ? '✓' : '' }}</span>
                <span>{{ task[0] }}</span>
              </div>
              <div class="task-meta">
                <span class="date">{{ task[1] }}</span>
                <span class="pill" :class="{ done: task[2] === 'Done' }">{{ task[2] }}</span>
                <span class="mini-avatar"></span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.interface {
  position: relative;
  overflow: hidden;
  padding: 112px 20px 132px;
  background: linear-gradient(to bottom, #0a0008 0%, #0f0a1a 45%, #5826a4 100%);
}

.interface::before {
  content: "";
  position: absolute;
  left: 50%;
  top: 120px;
  width: min(860px, 92vw);
  height: 680px;
  transform: translateX(-50%);
  border-radius: 50%;
  background: radial-gradient(circle, rgba(121, 56, 220, 0.34), transparent 66%);
  filter: blur(52px);
}

.section-heading,
.mockup-wrap {
  position: relative;
  z-index: 1;
}

.section-heading {
  width: min(540px, 100%);
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
  margin: 24px auto 0;
  color: rgba(255, 255, 255, 0.72);
  font-size: 16px;
  font-weight: 500;
  line-height: 1.55;
}

.mockup-wrap {
  width: min(1100px, 100%);
  margin: 66px auto 0;
  overflow: hidden;
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 12px;
  background: #0d0d14;
  box-shadow: 0 30px 90px rgba(0, 0, 0, 0.46), 0 0 90px rgba(168, 85, 247, 0.28);
}

.window-bar {
  height: 32px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 12px;
  background: #09090d;
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
}

.dots {
  display: flex;
  gap: 7px;
}

.dots span {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: #6b7280;
}

.search {
  width: 230px;
  height: 20px;
  padding: 0 10px;
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 6px;
  background: #16151c;
  color: rgba(255, 255, 255, 0.36);
  font-size: 10px;
  line-height: 18px;
}

.mockup-body {
  display: grid;
  grid-template-columns: 260px minmax(0, 1fr);
  min-height: 610px;
}

aside {
  position: relative;
  padding: 28px 20px;
  background: #0b0b12;
  border-right: 1px solid rgba(255, 255, 255, 0.06);
}

.workspace {
  margin-bottom: 18px;
  color: #fff;
  font-size: 13px;
}

nav {
  display: grid;
  gap: 5px;
}

nav a {
  display: flex;
  align-items: center;
  gap: 9px;
  padding: 10px 12px;
  border-radius: 9px;
  color: rgba(255, 255, 255, 0.68);
  font-size: 12px;
  font-weight: 600;
}

nav a.divider {
  margin-top: 18px;
}

nav a.active {
  background: #1e1830;
  color: #fff;
}

.avatar {
  position: absolute;
  left: 18px;
  bottom: 18px;
  width: 34px;
  height: 34px;
  border: 2px solid rgba(255, 255, 255, 0.16);
  border-radius: 50%;
  background: radial-gradient(circle at 30% 25%, #fbd38d, #7c3aed 58%, #111827);
}

.content {
  min-width: 0;
  padding: 34px 28px;
  background: #101018;
}

.breadcrumb {
  color: rgba(255, 255, 255, 0.42);
  font-size: 11px;
}

.title-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 14px;
  margin-top: 20px;
  color: rgba(255, 255, 255, 0.62);
}

h3 {
  margin: 0;
  color: #fff;
  font-size: 24px;
  font-weight: 800;
}

.group-label {
  padding: 26px 0 10px;
  color: rgba(255, 255, 255, 0.42);
  font-size: 11px;
  font-weight: 700;
}

.task-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  padding: 9px 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.045);
  color: rgba(255, 255, 255, 0.78);
  font-size: 12px;
}

.task-name,
.task-meta {
  display: flex;
  align-items: center;
  gap: 8px;
}

.task-name {
  min-width: 0;
}

.task-name span:last-child {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

.check {
  width: 15px;
  height: 15px;
  flex: 0 0 15px;
  display: grid;
  place-items: center;
  border: 1px solid rgba(255, 255, 255, 0.22);
  border-radius: 50%;
  color: #4ade80;
  font-size: 10px;
}

.check.done {
  background: rgba(74, 222, 128, 0.08);
}

.date {
  color: rgba(255, 255, 255, 0.45);
  white-space: nowrap;
}

.pill {
  border-radius: 999px;
  padding: 3px 8px;
  background: #1c1917;
  color: #fbbf24;
  font-size: 10px;
  font-weight: 700;
  white-space: nowrap;
}

.pill.done {
  background: #052e16;
  color: #4ade80;
}

.mini-avatar {
  width: 18px;
  height: 18px;
  border-radius: 50%;
  background: linear-gradient(135deg, #fde68a, #7c3aed);
}

@media (max-width: 860px) {
  .mockup-body {
    grid-template-columns: 1fr;
  }

  aside {
    display: none;
  }
}

@media (max-width: 640px) {
  .mockup-wrap {
    border-radius: 10px;
  }

  .search,
  .date,
  .mini-avatar {
    display: none;
  }

  .content {
    padding: 24px 18px;
  }

  .task-row {
    align-items: flex-start;
  }
}
</style>
