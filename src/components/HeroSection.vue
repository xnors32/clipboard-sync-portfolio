<script setup>
const stats = [
  { value: '2', label: 'Platforms' },
  { value: '<500ms', label: 'Sync Latency' },
  { value: 'Real-time', label: 'Firestore Sync' },
]
</script>

<template>
  <section id="overview" class="relative min-h-screen flex items-center justify-center overflow-hidden">
    <div class="absolute inset-0 pointer-events-none"
         style="background-image: linear-gradient(rgba(99,102,241,0.03) 1px, transparent 1px), linear-gradient(90deg, rgba(99,102,241,0.03) 1px, transparent 1px); background-size: 40px 40px;">
    </div>
    <div class="absolute inset-0 pointer-events-none">
      <div class="absolute top-1/4 left-1/4 w-96 h-96 bg-accent/10 rounded-full blur-3xl"></div>
      <div class="absolute bottom-1/4 right-1/4 w-72 h-72 bg-purple-500/10 rounded-full blur-3xl"></div>
    </div>

    <div class="relative max-w-4xl mx-auto px-4 sm:px-6 text-center pt-24">
      <div class="animate-fade-in">
        <span class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-accent/10 border border-accent/20 text-accent-light text-sm font-medium mb-8">
          <span class="w-2 h-2 bg-green-400 rounded-full animate-pulse"></span>
          Cross-Platform Clipboard Sync
        </span>
      </div>

      <h1 class="text-4xl sm:text-6xl lg:text-7xl font-extrabold tracking-tight leading-tight animate-fade-up">
        Sync your clipboard<br />
        <span class="bg-gradient-to-r from-accent via-purple-400 to-accent bg-clip-text text-transparent">across every device</span>
      </h1>

      <p class="mt-6 text-lg sm:text-xl text-surface-200 max-w-2xl mx-auto leading-relaxed animate-fade-up animation-delay-200">
        A lightweight ecosystem that keeps your clipboard in sync between your
        <strong class="text-white">Linux desktop</strong> and <strong class="text-white">Android device</strong>
        through Firebase Firestore — fast, private, and seamless.
      </p>

      <div class="mt-10 flex flex-col sm:flex-row items-center justify-center gap-4 animate-fade-up animation-delay-300">
        <a href="#projects" class="w-full sm:w-auto inline-flex items-center justify-center gap-2 px-8 py-3.5 bg-accent hover:bg-accent-dark text-white font-semibold rounded-xl transition-colors">
          Explore Projects
          <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/>
          </svg>
        </a>
        <a href="https://github.com/xnors32" target="_blank" class="w-full sm:w-auto inline-flex items-center justify-center gap-2 px-8 py-3.5 bg-white/5 hover:bg-white/10 text-white font-semibold rounded-xl border border-white/10 transition-colors">
          <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
            <path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/>
          </svg>
          GitHub
        </a>
      </div>

      <div class="mt-20 flex items-center justify-center gap-8 sm:gap-16 text-surface-200 animate-fade-up animation-delay-500">
        <template v-for="(stat, i) in stats" :key="stat.label">
          <div v-if="i > 0" class="w-px h-10 bg-white/10"></div>
          <div class="text-center">
            <div class="text-2xl sm:text-3xl font-bold text-white">{{ stat.value }}</div>
            <div class="text-xs sm:text-sm mt-1">{{ stat.label }}</div>
          </div>
        </template>
      </div>
    </div>
  </section>
</template>
