<script setup>
const rows = [
  { feature: 'Clipboard Monitoring', desktop: true, android: false },
  { feature: 'Upload to Firestore', desktop: true, android: false },
  { feature: 'Real-time Listener', desktop: false, android: true },
  { feature: 'Background Sync', desktop: 'systemd', android: 'WorkManager' },
  { feature: 'Auth Support', desktop: 'Dev Token', android: 'Email/Password' },
  { feature: 'Auto Cleanup', desktop: true, android: true },
  { feature: 'Dark/Light Theme', desktop: false, android: true },
  { feature: 'Pull to Refresh', desktop: false, android: true },
  { feature: 'Delete Items', desktop: false, android: true },
  { feature: 'Config File', desktop: 'TOML', android: 'In-app' },
  { feature: 'Multi-backend (wl/x11)', desktop: true, android: false },
  { feature: 'Material 3 UI', desktop: false, android: true },
]
</script>

<template>
  <section id="features" class="py-24 sm:py-32 relative">
    <div class="absolute inset-0 pointer-events-none">
      <div class="absolute top-0 left-1/2 -translate-x-1/2 w-full h-px bg-gradient-to-r from-transparent via-accent/30 to-transparent"></div>
    </div>
    <div class="max-w-4xl mx-auto px-4 sm:px-6">
      <div class="text-center mb-16" data-anim="animate-fade-up">
        <span class="text-accent-light text-sm font-semibold tracking-widest uppercase">Comparison</span>
        <h2 class="mt-3 text-3xl sm:text-5xl font-bold tracking-tight">Feature breakdown</h2>
      </div>

      <div class="bg-white/5 backdrop-blur-xl border border-white/10 rounded-2xl overflow-hidden" data-anim="animate-fade-up animation-delay-200">
        <div class="overflow-x-auto">
          <table class="w-full text-sm">
            <thead>
              <tr class="border-b border-white/5">
                <th class="text-left p-4 sm:p-6 font-semibold text-surface-200">Feature</th>
                <th class="text-center p-4 sm:p-6 font-semibold text-orange-400">Desktop</th>
                <th class="text-center p-4 sm:p-6 font-semibold text-green-400">Android</th>
              </tr>
            </thead>
            <tbody>
              <tr
                v-for="(row, i) in rows"
                :key="i"
                class="border-b border-white/5 last:border-0 hover:bg-white/[0.02] transition-colors"
              >
                <td class="p-4 sm:p-6 text-surface-200">{{ row.feature }}</td>
                <td class="p-4 sm:p-6 text-center">
                  <span v-if="row.desktop === true" class="text-green-400">&#10003;</span>
                  <span v-else-if="row.desktop === false" class="text-surface-700">&mdash;</span>
                  <span v-else class="text-surface-200 text-xs">{{ row.desktop }}</span>
                </td>
                <td class="p-4 sm:p-6 text-center">
                  <span v-if="row.android === true" class="text-green-400">&#10003;</span>
                  <span v-else-if="row.android === false" class="text-surface-700">&mdash;</span>
                  <span v-else class="text-surface-200 text-xs">{{ row.android }}</span>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </section>
</template>
