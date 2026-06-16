<script setup>
import { ref } from 'vue'

const mobileMenu = ref(false)

const links = [
  { href: '#overview', label: 'Overview' },
  { href: '#architecture', label: 'Architecture' },
  { href: '#projects', label: 'Projects' },
  { href: '#features', label: 'Features' },
]
</script>

<template>
  <nav class="fixed top-0 w-full z-50 bg-white/5 backdrop-blur-xl border-b border-white/5">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 py-4 flex items-center justify-between">
      <a href="#" class="text-lg font-bold tracking-tight">
        <span class="bg-gradient-to-r from-accent to-purple-400 bg-clip-text text-transparent">Clipboard</span>
        <span class="text-surface-200">Sync</span>
      </a>

      <div class="hidden sm:flex items-center gap-6 text-sm text-surface-200">
        <a
          v-for="link in links"
          :key="link.href"
          :href="link.href"
          class="hover:text-white transition-colors"
        >
          {{ link.label }}
        </a>
      </div>

      <button @click="mobileMenu = !mobileMenu" class="sm:hidden text-surface-200 hover:text-white">
        <svg v-if="!mobileMenu" class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
        </svg>
        <svg v-else class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
        </svg>
      </button>
    </div>

    <Transition
      enter-active-class="transition duration-200 ease-out"
      enter-from-class="opacity-0 -translate-y-2"
      enter-to-class="opacity-100 translate-y-0"
      leave-active-class="transition duration-150 ease-in"
      leave-from-class="opacity-100 translate-y-0"
      leave-to-class="opacity-0 -translate-y-2"
    >
      <div v-if="mobileMenu" class="sm:hidden border-t border-white/5 px-4 pb-4">
        <a
          v-for="link in links"
          :key="link.href"
          :href="link.href"
          @click="mobileMenu = false"
          class="block py-3 text-sm text-surface-200 hover:text-white transition-colors"
        >
          {{ link.label }}
        </a>
      </div>
    </Transition>
  </nav>
</template>
