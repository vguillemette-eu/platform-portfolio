<script setup lang="ts">

const config = useRuntimeConfig()
const appVersion = config.public.appVersion
const buildDate = config.public.buildDate

const roadmapSprints = [
  {
    sprint: 'Sprint 1',
    title: 'Socle Infra & Premier Déploiement',
    status: 'completed',
    badge: 'Live',
    details: 'Cluster K3s HA (OVHcloud), MiniPC Proxmox VE local, Mesh Tailscale & Pipeline CI/CD.'
  },
  {
    sprint: 'Sprint 2',
    title: 'Ingress, TLS & Continuous Deployment',
    status: 'current',
    badge: 'En cours',
    details: 'Cilium Envoy Gateway API, Cert-Manager Let\'s Encrypt & GitOps ArgoCD.'
  },
  {
    sprint: 'Sprint 3',
    title: 'Observabilité Centralisée',
    status: 'upcoming',
    badge: 'À venir',
    details: 'Prometheus & Loki sur Proxmox VE local, remontée des métriques OVHcloud via Tailscale.'
  },
  {
    sprint: 'Sprint 4 & 5',
    title: 'APIs Métier & Passthrough iGPU',
    status: 'upcoming',
    badge: 'À venir',
    details: 'Backend .NET 10, Go Exporter, Vue Flow C4 et accélération ROCm sur Radeon 780M.'
  },
  {
    sprint: 'Sprint 6',
    title: 'Chatbot RAG IA & Pipeline Vectorielle',
    status: 'upcoming',
    badge: 'À venir',
    details: 'Vectorisation documentaire On-Premise, base Qdrant et assistant RAG Ollama.'
  }
]
</script>

<template>
  <div class="space-y-16 py-8 max-w-5xl mx-auto px-4">
    
    <!-- 1. HERO TEASER -->
    <section class="text-center space-y-6 max-w-3xl mx-auto">
      <!-- Badge Release Status -->
      <div class="inline-flex items-center gap-2 px-3 py-1.5 rounded-full text-xs font-mono bg-neutral-100 dark:bg-neutral-800 border border-neutral-200 dark:border-neutral-700">
        <span class="relative flex h-2.5 w-2.5">
          <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
          <span class="relative inline-flex rounded-full h-2.5 w-2.5 bg-emerald-500"></span>
        </span>
        <span class="text-neutral-600 dark:text-neutral-300">
          Premier Pod Déployé 
        </span>
      </div>

      <!-- Main Headline -->
      <h1 class="text-4xl sm:text-6xl font-extrabold tracking-tight text-neutral-900 dark:text-white">
        Platform Portfolio <br />
        <span class="bg-linear-to-r from-primary-500 to-indigo-600 bg-clip-text text-transparent">
          En Construction Live
        </span>
      </h1>

      <!-- Teaser Pitch -->
      <p class="text-lg sm:text-xl text-neutral-600 dark:text-neutral-300 leading-relaxed">
        Vous naviguez sur la première version d'un démonstrateur Cloud-Native & DevSecOps. <br />
        Cette plateforme évoluera en direct au fil des sprints sur une infrastructure hybride 2-Tier (K3s HA OVHcloud & Proxmox VE On-Premise).
      </p>

      <!-- Infos Déploiement -->
      <div class="pt-2 text-xs font-mono text-neutral-400 flex items-center justify-center gap-4">
        <span>Version: {{ appVersion }}</span>
        <span>•</span>
        <span>Livré le: {{ buildDate }}</span>
      </div>
    </section>

    <!-- 2. PILIERS EN COURS DE BOOTSTRAP -->
    <section class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <UCard>
        <template #header>
          <div class="flex items-center gap-3">
            <UIcon name="i-heroicons-server-stack" class="w-6 h-6 text-primary-500" />
            <h3 class="font-bold text-base text-neutral-900 dark:text-white">Infra Hybride</h3>
          </div>
        </template>
        <p class="text-xs text-neutral-600 dark:text-neutral-300 leading-relaxed">
          Cluster K3s 3 nœuds sur OVHcloud interconnecté en mesh Tailscale WireGuard à un hyperviseur Proxmox VE.
        </p>
      </UCard>

      <UCard>
        <template #header>
          <div class="flex items-center gap-3">
            <UIcon name="i-heroicons-arrow-path" class="w-6 h-6 text-indigo-500" />
            <h3 class="font-bold text-base text-neutral-900 dark:text-white">GitOps & Delivery</h3>
          </div>
        </template>
        <p class="text-xs text-neutral-600 dark:text-neutral-300 leading-relaxed">
          Déploiement automatisé depuis notre forge On-Premise (Forgejo) vers le cluster public.
        </p>
      </UCard>

      <UCard>
        <template #header>
          <div class="flex items-center gap-3">
            <UIcon name="i-heroicons-cpu-chip" class="w-6 h-6 text-violet-500" />
            <h3 class="font-bold text-base text-neutral-900 dark:text-white">IA & Métriques (À venir)</h3>
          </div>
        </template>
        <p class="text-xs text-neutral-600 dark:text-neutral-300 leading-relaxed">
          Intégration future d'un Assistant RAG (Ollama + Qdrant) et accélération ROCm sur iGPU Radeon 780M.
        </p>
      </UCard>
    </section>

    <!-- 3. ROADMAP DES LIVRAISONS -->
    <section class="space-y-6">
      <div class="text-center space-y-2">
        <h2 class="text-2xl font-bold text-neutral-900 dark:text-white">
          Carnet de Bord & Roadmap
        </h2>
        <p class="text-sm text-neutral-500">
          Suivez la construction progressive de l'architecture étape par étape.
        </p>
      </div>

      <div class="space-y-4 max-w-3xl mx-auto">
        <div 
          v-for="item in roadmapSprints" 
          :key="item.sprint"
          class="p-4 rounded-xl border transition-all"
          :class="[
            item.status === 'completed' 
              ? 'bg-primary-500/5 border-primary-500/30 dark:bg-primary-950/10' 
              : item.status === 'current' 
                ? 'bg-primary-50 dark:bg-primary-900/10 border-primary-200 dark:border-primary-800'
              : 'bg-neutral-50 dark:bg-neutral-900/50 border-neutral-200 dark:border-neutral-800'
          ]"
        >
          <div class="flex items-center justify-between gap-4 mb-2">
            <div class="flex items-center gap-3">
              <UIcon 
                :name="item.status === 'completed' ? 'i-heroicons-check-circle' : item.status === 'current' ? 'i-heroicons-arrow-path' : 'i-heroicons-clock'" 
                :class="item.status === 'completed' ? 'text-primary-500' : item.status === 'current' ? 'text-success-500' : 'text-neutral-400'"
                class="w-5 h-5"
              />
              <span class="font-bold text-sm text-neutral-900 dark:text-white">{{ item.sprint }}</span>
            </div>
            <UBadge 
              :color="item.status === 'completed' ? 'primary' : item.status === 'current' ? 'success' : 'neutral'" 
              variant="soft" 
              size="xs"
            >
              {{ item.badge }}
            </UBadge>
          </div>
          
          <h4 class="font-semibold text-sm text-neutral-800 dark:text-neutral-200 mb-1 ml-8">
            {{ item.title }}
          </h4>
          <p class="text-xs text-neutral-500 dark:text-neutral-400 ml-8">
            {{ item.details }}
          </p>
        </div>
      </div>
    </section>

  </div>
</template>