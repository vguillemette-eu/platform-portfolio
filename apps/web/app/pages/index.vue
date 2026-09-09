<template>
  <main class="min-h-screen bg-slate-900 text-slate-100 flex flex-col items-center justify-center p-6">
    <div class="max-w-2xl w-full space-y-6 text-center">
      <h1 class="text-4xl font-extrabold tracking-tight text-emerald-400 sm:text-5xl">
        Platform Portfolio
      </h1>
      <p class="text-lg text-slate-300">
        Socle Cloud-Native Hybride & Pipeline AI
      </p>

      <!-- Dashboard Status minimal (J+14) -->
      <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 mt-8 text-left">
        <div class="p-4 rounded-xl bg-slate-800 border border-slate-700">
          <div class="flex items-center space-x-2">
            <span class="h-3 w-3 rounded-full bg-emerald-500 animate-pulse"></span>
            <span class="font-semibold text-slate-200">Cluster K3s OVH</span>
          </div>
          <p class="text-xs text-slate-400 mt-2">Statut : Opérationnel (2 CP + 1 Worker)</p>
        </div>

        <div class="p-4 rounded-xl bg-slate-800 border border-slate-700">
          <div class="flex items-center space-x-2">
            <span class="h-3 w-3 rounded-full bg-emerald-500 animate-pulse"></span>
            <span class="font-semibold text-slate-200">MiniPC On-Premise</span>
          </div>
          <p class="text-xs text-slate-400 mt-2">Tailscale Mesh : Connecté</p>
        </div>
      </div>
    </div>
  </main>
</template>