<script setup>
const techStack = [
  { name: 'Rust', icon: '/material-icon-theme--rust.svg', role: 'Desktop' },
  { name: 'Kotlin', icon: '/material-icon-theme--kotlin.svg', role: 'Android' },
  { name: 'Firestore', icon: '/gcp--firestore.svg', role: 'Database' },
  { name: 'Compose', icon: '/devicon--jetpackcompose.svg', role: 'UI' },
  { name: 'Linux', icon: '/Linux.svg', role: 'Platform' },
  { name: 'Firebase', icon: '/material-icon-theme--firebase.svg', role: 'Backend' },
]
</script>

<template>
  <section class="py-24 sm:py-32 relative">
    <div class="absolute inset-0 pointer-events-none">
      <div class="absolute top-0 left-1/2 -translate-x-1/2 w-full h-px bg-gradient-to-r from-transparent via-accent/30 to-transparent"></div>
    </div>
    <div class="max-w-6xl mx-auto px-4 sm:px-6">
      <div class="text-center mb-16" data-anim="animate-fade-up">
        <span class="text-accent-light text-sm font-semibold tracking-widest uppercase">Tech Stack</span>
        <h2 class="mt-3 text-3xl sm:text-5xl font-bold tracking-tight">Built with modern tools</h2>
      </div>

      <div class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-6 gap-4">
        <div
          v-for="(tech, i) in techStack"
          :key="tech.name"
          class="bg-white/5 backdrop-blur-xl border border-white/10 rounded-xl p-5 text-center hover:-translate-y-1 hover:shadow-xl hover:shadow-black/20 transition-all duration-300"
          :data-anim="`animate-fade-up animation-delay-${(i + 1) * 100}`"
        >
          <img :src="tech.icon" :alt="tech.name" class="w-10 h-10 mx-auto mb-2" />
          <div class="text-sm font-semibold">{{ tech.name }}</div>
          <div class="text-xs text-surface-200 mt-1">{{ tech.role }}</div>
        </div>
      </div>
    </div>
  </section>
</template>
