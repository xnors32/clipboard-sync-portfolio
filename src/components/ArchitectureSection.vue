<script setup>
const nodes = [
  {
    title: 'Desktop Daemon',
    desc: 'Rust binary monitors clipboard via wl-paste, xclip, or cliphist',
    tags: ['Rust', 'Linux'],
    tagColor: 'bg-orange-500/10 text-orange-300',
    iconBg: 'bg-orange-500/10',
    iconColor: 'text-orange-400',
    icon: 'M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z',
  },
  {
    title: 'Firebase Firestore',
    desc: 'Real-time cloud database stores clipboard items per user',
    tags: ['REST API', 'Real-time'],
    tagColor: 'bg-amber-500/10 text-amber-300',
    iconBg: 'bg-amber-500/10',
    iconColor: 'text-amber-400',
    icon: 'M4 7v10c0 2.21 3.582 4 8 4s8-1.79 8-4V7M4 7c0 2.21 3.582 4 8 4s8-1.79 8-4M4 7c0-2.21 3.582-4 8-4s8 1.79 8 4m0 5c0 2.21-3.582 4-8 4s-8-1.79-8-4',
  },
  {
    title: 'Android App',
    desc: 'Material 3 app with real-time listener and background sync',
    tags: ['Kotlin', 'Compose'],
    tagColor: 'bg-green-500/10 text-green-300',
    iconBg: 'bg-green-500/10',
    iconColor: 'text-green-400',
    icon: 'M12 18h.01M8 21h8a2 2 0 002-2V5a2 2 0 00-2-2H8a2 2 0 00-2 2v14a2 2 0 002 2z',
  },
]

const dataStructure = `users/{userId}/
  clipboard/
    items/{documentId}
      ├── content:       "copied text"
      ├── type:          "text"
      ├── timestamp:     1700000000
      ├── deviceSource:  "my-laptop"
      ├── fileUrl:       null
      ├── fileName:      null
      └── fileSize:      null`
</script>

<template>
  <section id="architecture" class="py-24 sm:py-32 relative">
    <div class="max-w-6xl mx-auto px-4 sm:px-6">
      <div class="text-center mb-16" data-anim="animate-fade-up">
        <span class="text-accent-light text-sm font-semibold tracking-widest uppercase">Architecture</span>
        <h2 class="mt-3 text-3xl sm:text-5xl font-bold tracking-tight">How it works</h2>
        <p class="mt-4 text-surface-200 max-w-xl mx-auto">
          Clipboard data flows through Firebase Firestore, keeping your devices in perfect sync.
        </p>
      </div>

      <div class="grid md:grid-cols-3 gap-6 items-center">
        <div
          v-for="(node, i) in nodes"
          :key="node.title"
          class="bg-white/5 backdrop-blur-xl border border-white/10 rounded-2xl p-8 text-center hover:-translate-y-1 hover:shadow-xl hover:shadow-black/20 transition-all duration-300"
          :data-anim="i === 0 ? 'animate-slide-right animation-delay-200' : i === 2 ? 'animate-slide-left animation-delay-200' : 'animate-fade-up animation-delay-300'"
        >
          <div class="w-16 h-16 mx-auto mb-4 rounded-2xl flex items-center justify-center" :class="node.iconBg">
            <svg class="w-8 h-8" :class="node.iconColor" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" :d="node.icon"/>
            </svg>
          </div>
          <h3 class="text-lg font-bold">{{ node.title }}</h3>
          <p class="text-sm text-surface-200 mt-2">{{ node.desc }}</p>
          <div class="mt-4 flex flex-wrap justify-center gap-2">
            <span v-for="tag in node.tags" :key="tag" class="inline-flex items-center px-2.5 py-0.5 rounded-full text-xs font-medium" :class="node.tagColor">
              {{ tag }}
            </span>
          </div>
        </div>
      </div>

      <div class="mt-12 bg-white/5 backdrop-blur-xl border border-white/10 rounded-2xl p-6 sm:p-8 max-w-2xl mx-auto" data-anim="animate-fade-up animation-delay-400">
        <h4 class="text-sm font-semibold text-accent-light uppercase tracking-wider mb-4">Data Structure</h4>
        <pre class="text-xs sm:text-sm font-mono text-surface-200 overflow-x-auto"><code>{{ dataStructure }}</code></pre>
      </div>
    </div>
  </section>
</template>
