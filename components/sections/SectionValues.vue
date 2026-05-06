<script setup>
import { Leaf, Shield, Award } from 'lucide-vue-next'

const values = [
  {
    title: 'Respect de la Nature',
    description: "Nos chevaux vivent en troupeau avec accès libre au foin. Leurs besoins physiologiques et psychologiques sont notre priorité.",
    icon: Leaf,
  },
  {
    title: 'Sécurité & Confiance',
    description: "Des installations entretenues et une cavalerie de qualité pour vous permettre de progresser dans les meilleures conditions.",
    icon: Shield,
  },
  {
    title: 'Excellence Pédagogique',
    description: "Une équipe diplômée et passionnée qui transmet l'art de l'équitation avec patience et professionnalisme.",
    icon: Award,
  },
]
</script>

<template>
  <AppSection id="values" variant="accent" class="relative overflow-hidden">
    <div class="absolute right-0 top-0 -translate-y-1/2 translate-x-1/3 opacity-5">
      <svg width="600" height="600" viewBox="0 0 100 100" class="text-primary fill-current">
        <path d="M50 0 L100 50 L50 100 L0 50 Z" />
      </svg>
    </div>
    <div class="grid lg:grid-cols-3 gap-12 lg:gap-8">
      <div v-for="(value, index) in values" :key="index" class="text-center group">
        <div class="mx-auto w-20 h-20 rounded-2xl bg-white shadow-soft flex items-center justify-center mb-8 rotate-3 group-hover:-rotate-3 transition-transform duration-300">
          <component :is="value.icon" class="text-primary" :size="32" />
        </div>
        <h3 class="text-2xl font-serif font-bold text-primary mb-4">{{ value.title }}</h3>
        <p class="text-text/80 leading-relaxed max-w-sm mx-auto">{{ value.description }}</p>
      </div>
    </div>
  </AppSection>
</template>
