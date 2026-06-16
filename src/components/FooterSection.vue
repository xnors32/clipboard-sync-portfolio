<template>
  <footer class="border-t border-white/5 py-12">
    <div class="max-w-6xl mx-auto px-4 sm:px-6">
      <div class="flex flex-col sm:flex-row items-center justify-between gap-6">
        <div>
          <span class="text-lg font-bold">
            <span class="bg-gradient-to-r from-accent to-purple-400 bg-clip-text text-transparent">Clipboard</span>
            <span class="text-surface-200">Sync</span>
          </span>
          <p class="text-sm text-surface-200 mt-1">Open-source clipboard sync ecosystem</p>
        </div>
        <div class="flex items-center gap-6">
          <a href="https://github.com/xnors32/clipboard-sync-desktop" target="_blank" class="text-surface-200 hover:text-white transition-colors text-sm">Desktop Repo</a>
          <a href="https://github.com/xnors32/sync-clipboard-android" target="_blank" class="text-surface-200 hover:text-white transition-colors text-sm">Android Repo</a>
          <a href="https://github.com/xnors32" target="_blank" class="text-surface-200 hover:text-white transition-colors text-sm">GitHub Profile</a>
        </div>
      </div>
      <div class="mt-8 pt-8 border-t border-white/5 text-center text-xs text-surface-700">
        Built with Vue 3 + Tailwind CSS &middot; MIT License
      </div>
    </div>
  </footer>
</template>
