<script setup lang="ts">
import { onMounted, onUnmounted, ref } from 'vue'
import HelloWorld from './components/HelloWorld.vue'
import ProposDeMoi from './components/ProposDeMoi.vue'
import QuickLinks from './components/QuickLinks.vue'

type SectionId = 'home' | 'apropos' | 'liens'

const activeSection = ref<SectionId>('home')
const sectionIds: SectionId[] = ['home', 'apropos', 'liens']
let observer: IntersectionObserver | null = null

const scrollToSection = (targetId: SectionId) => {
  const target = document.getElementById(targetId)
  if (!target) {
    return
  }

  const nav = document.querySelector('.top-nav') as HTMLElement | null
  const navHeight = nav?.offsetHeight ?? 0
  const top = target.getBoundingClientRect().top + window.scrollY

  window.scrollTo({
    top: Math.max(top - navHeight - 10, 0),
    behavior: 'smooth',
  })

  activeSection.value = targetId
}

onMounted(() => {
  // Prevent browser from restoring previous scroll position on refresh.
  if ('scrollRestoration' in history) {
    history.scrollRestoration = 'manual'
  }

  window.scrollTo({ top: 0, left: 0, behavior: 'auto' })

  observer = new IntersectionObserver(
    (entries) => {
      const visible = entries
        .filter((entry) => entry.isIntersecting)
        .sort((a, b) => b.intersectionRatio - a.intersectionRatio)

      if (visible.length === 0) {
        return
      }

      const firstVisible = visible[0]
      if (!firstVisible) {
        return
      }

      const id = firstVisible.target.id as SectionId
      if (sectionIds.includes(id)) {
        activeSection.value = id
      }
    },
    { threshold: [0.35, 0.6, 0.8] }
  )

  sectionIds.forEach((id) => {
    const el = document.getElementById(id)
    if (el) {
      observer?.observe(el)
    }
  })
})

onUnmounted(() => {
  observer?.disconnect()
})
</script>

<template>
  <nav class="top-nav" aria-label="Navigation principale">
    <a href="#home" :class="{ active: activeSection === 'home' }" @click.prevent="scrollToSection('home')">Haut de la page</a>
    <a href="#apropos" :class="{ active: activeSection === 'apropos' }" @click.prevent="scrollToSection('apropos')">À propos de moi</a>
    <a href="#liens" :class="{ active: activeSection === 'liens' }" @click.prevent="scrollToSection('liens')">Mes liens</a>
  </nav>

  <main class="page-stack">
    <section id="home" class="page-section" :class="{ 'is-active': activeSection === 'home' }">
      <div class="section-content">
        <HelloWorld msg="Bienvenue sur mon Portfolio" />
      </div>
    </section>

    <section id="apropos" class="page-section" :class="{ 'is-active': activeSection === 'apropos' }">
      <div class="section-content">
        <ProposDeMoi msg="À propos de moi." />
      </div>
    </section>

    <section id="liens" class="page-section" :class="{ 'is-active': activeSection === 'liens' }">
      <div class="section-content">
        <QuickLinks />
      </div>
    </section>
  </main>
</template>

<style scoped>
:global(html) {
  scroll-behavior: smooth;
  scroll-snap-type: y proximity;
}

:global(body) {
  margin: 0;
}

.top-nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 20;
  display: flex;
  justify-content: center;
  gap: 0.8rem;
  padding: 0.9rem 1rem;
  background-color: rgba(8, 10, 18, 0.45);
  backdrop-filter: blur(4px);
}

.top-nav a {
  color: #fff;
  text-decoration: none;
  border-radius: 999px;
  padding: 0.35rem 0.8rem;
  border: 1px solid rgba(255, 255, 255, 0.35);
  transition: background-color 0.25s ease, transform 0.25s ease, border-color 0.25s ease;
}

.top-nav a:hover {
  background-color: rgba(255, 255, 255, 0.12);
  border-color: rgba(255, 255, 255, 0.55);
  transform: translateY(-1px);
}

.top-nav a.active {
  background-color: rgba(255, 255, 255, 0.18);
  border-color: rgba(255, 255, 255, 0.72);
}

.page-stack {
  line-height: 1.5;
}

.page-section {
  min-height: 100vh;
  scroll-snap-align: start;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 5rem 1rem 1rem;
  opacity: 0.55;
  transition: opacity 0.45s ease;
}

.section-content {
  width: 100%;
  display: flex;
  justify-content: center;
  transform: translateY(20px);
  opacity: 0;
  transition: transform 0.45s ease, opacity 0.45s ease;
}

.page-section.is-active {
  opacity: 1;
}

.page-section.is-active .section-content {
  transform: translateY(0);
  opacity: 1;
}

@media (max-width: 768px) {
  .top-nav {
    gap: 0.45rem;
    padding: 0.75rem 0.6rem;
  }

  .top-nav a {
    font-size: 0.9rem;
    padding: 0.32rem 0.62rem;
  }
}
</style>
