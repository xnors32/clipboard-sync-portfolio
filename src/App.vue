<script setup>
import { onMounted } from 'vue'
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import ArchitectureSection from './components/ArchitectureSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import FeaturesSection from './components/FeaturesSection.vue'
import TechStackSection from './components/TechStackSection.vue'
import FooterSection from './components/FooterSection.vue'

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          const el = entry.target
          const anim = el.dataset.anim || 'animate-fade-up'
          anim.split(' ').forEach((cls) => el.classList.add(cls))
          observer.unobserve(el)
        }
      })
    },
    { threshold: 0.15 }
  )

  document.querySelectorAll('[data-anim]').forEach((el) => {
    observer.observe(el)
  })
})
</script>

<template>
  <NavBar />
  <HeroSection />
  <ArchitectureSection />
  <ProjectsSection />
  <FeaturesSection />
  <TechStackSection />
  <FooterSection />
</template>
