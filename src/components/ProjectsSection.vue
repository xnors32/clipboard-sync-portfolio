<script setup>
const projects = [
  {
    title: 'Clipboard Sync Desktop',
    desc: 'A Rust daemon that monitors your Linux clipboard and syncs changes to Firebase Firestore in real-time. Supports Wayland, X11, and cliphist backends.',
    repo: 'https://github.com/xnors32/clipboard-sync-desktop',
    tags: ['Rust', 'wl-clipboard', 'xclip', 'Firestore REST', 'TOML'],
    features: [
      'Clipboard polling every 500ms',
      'Auto-cleanup with configurable retention',
      'TOML-based configuration',
      'systemd service support',
    ],
    iconBg: 'bg-orange-500/10',
    iconColor: 'text-orange-400',
    icon: 'M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z',
    animClass: 'animate-slide-right animation-delay-200',
  },
  {
    title: 'Clipboard Sync Android',
    desc: 'A Material 3 Android companion app that reads clipboard items from Firestore in real-time. Clean UI with dark/light theme and background sync.',
    repo: 'https://github.com/xnors32/sync-clipboard-android',
    tags: ['Kotlin', 'Jetpack Compose', 'Material 3', 'Firebase Auth', 'WorkManager'],
    features: [
      'Real-time Firestore snapshot listener',
      'Firebase Auth (email/password)',
      'Background sync via WorkManager',
      'Material 3 with Dark/Light theme',
    ],
    iconBg: 'bg-green-500/10',
    iconColor: 'text-green-400',
    icon: 'M12 18h.01M8 21h8a2 2 0 002-2V5a2 2 0 00-2-2H8a2 2 0 00-2 2v14a2 2 0 002 2z',
    animClass: 'animate-slide-left animation-delay-200',
  },
]
</script>

<template>
  <section id="projects" class="py-24 sm:py-32 relative">
    <div class="absolute inset-0 pointer-events-none">
      <div class="absolute top-0 left-1/2 -translate-x-1/2 w-full h-px bg-gradient-to-r from-transparent via-accent/30 to-transparent"></div>
    </div>
    <div class="max-w-6xl mx-auto px-4 sm:px-6">
      <div class="text-center mb-16" data-anim="animate-fade-up">
        <span class="text-accent-light text-sm font-semibold tracking-widest uppercase">Projects</span>
        <h2 class="mt-3 text-3xl sm:text-5xl font-bold tracking-tight">Two apps, one ecosystem</h2>
      </div>

      <div class="grid lg:grid-cols-2 gap-8">
        <div
          v-for="project in projects"
          :key="project.title"
          class="bg-white/5 backdrop-blur-xl border border-white/10 rounded-2xl overflow-hidden hover:-translate-y-1 hover:shadow-2xl hover:shadow-black/20 transition-all duration-300"
          :data-anim="project.animClass"
        >
          <div class="p-8">
            <div class="flex items-start justify-between mb-6">
              <div class="w-14 h-14 rounded-2xl flex items-center justify-center" :class="project.iconBg">
                <svg class="w-7 h-7" :class="project.iconColor" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" :d="project.icon"/>
                </svg>
              </div>
              <span class="inline-flex items-center px-2.5 py-0.5 rounded-full text-xs font-medium bg-green-500/10 text-green-300">Active</span>
            </div>

            <h3 class="text-2xl font-bold mb-2">{{ project.title }}</h3>
            <p class="text-surface-200 leading-relaxed mb-6">{{ project.desc }}</p>

            <div class="space-y-3 mb-6">
              <div v-for="feat in project.features" :key="feat" class="flex items-center gap-3 text-sm">
                <svg class="w-4 h-4 text-accent-light shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/>
                </svg>
                <span class="text-surface-200">{{ feat }}</span>
              </div>
            </div>

            <div class="flex flex-wrap gap-2 mb-6">
              <span v-for="tag in project.tags" :key="tag" class="inline-flex items-center px-2.5 py-0.5 rounded-full text-xs font-medium bg-white/5 text-surface-200">
                {{ tag }}
              </span>
            </div>

            <a
              :href="project.repo"
              target="_blank"
              class="inline-flex items-center gap-2 px-5 py-2.5 bg-accent hover:bg-accent-dark text-white text-sm font-semibold rounded-xl transition-colors"
            >
              <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/>
              </svg>
              View Repository
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
