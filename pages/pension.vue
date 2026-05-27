<script setup>
import { Home, Leaf, Shield, Heart } from 'lucide-vue-next'

useSeoMeta({
  title: "Pension pour chevaux avec accès aux propriétaires | Écurie - Élevage d'Elphe",
  description: "Pension pour chevaux en paddock ou en box à l'Écurie Elphé. Sorties quotidiennes, surveillance 24h/7 et foin à volonté.",
})

const atouts = [
  { icon: Home, title: 'Box & Paddock', description: "Nous proposons des pensions sous différentes formules : pré / box, adaptées aux besoins de chaque cheval. Chaque espace est entretenu quotidiennement." },
  { icon: Leaf, title: 'Foin à volonté', description: "Nos pensionnaires ont accès au foin à volonté, conformément aux besoins physiologiques naturels du cheval. Une alimentation saine et équilibrée." },
  { icon: Shield, title: 'Surveillance 24h/7', description: "Votre cheval est surveillé en permanence. Nous assurons un suivi quotidien de son état de santé, de son comportement et de son bien-être." },
  { icon: Heart, title: 'Sorties quotidiennes', description: "Chaque pensionnaire bénéficie de sorties quotidiennes au pré ou en paddock pour préserver son équilibre physique et psychologique." },
]

const galerie = [
  { src: '/images/Champ.jpg', alt: 'Chevaux au pré en pension' },
  { src: '/images/Horse_group.jpg', alt: 'Groupe de chevaux en paddock' },
  { src: '/images/Gray_horse_2.jpg', alt: "Cheval en pension à l'Écurie Elphé" },
  { src: '/images/Two_horse.jpg', alt: 'Deux chevaux ensemble au pré' },
]
</script>

<template>
  <div>
    <!-- Hero -->
    <div class="relative h-[50vh] min-h-[400px] flex items-center justify-center overflow-hidden">
      <img src="/images/Champ.jpg" alt="Pension chevaux à l'Écurie Elphe" class="absolute inset-0 w-full h-full object-cover object-center" fetchpriority="high" />
      <div class="absolute inset-0 bg-primary/50 mix-blend-multiply z-10" />
      <div class="absolute inset-0 bg-gradient-to-t from-primary/70 via-transparent to-transparent z-10" />
      <div class="relative z-20 text-center text-white px-4">
        <span class="inline-block text-accent font-medium tracking-widest uppercase text-sm mb-4 drop-shadow-md">Écurie - Élevage d'Elphe</span>
        <h1 class="text-4xl md:text-6xl font-serif font-bold drop-shadow-lg">Pension pour chevaux avec accès aux propriétaires</h1>
      </div>
    </div>

    <!-- Introduction -->
    <AppSection variant="light">
      <div class="grid md:grid-cols-2 gap-12 lg:gap-20 items-center">
        <div class="relative">
          <div class="aspect-[4/5] rounded-2xl overflow-hidden shadow-2xl relative z-10">
            <img src="/images/Horse_group.jpg" alt="Chevaux en pension à l'Écurie Elphe" loading="lazy" class="w-full h-full object-cover" />
          </div>
          <div class="absolute top-10 -left-6 md:-left-10 w-full h-full border-4 border-accent/30 rounded-2xl -z-10" />
          <div class="absolute -bottom-8 -right-8 w-48 h-48 bg-primary/5 rounded-full blur-3xl -z-10" />
        </div>
        <div class="space-y-8">
          <span class="text-secondary font-medium tracking-wider uppercase text-sm block">Notre offre</span>
          <p class="text-xl text-primary font-serif font-medium leading-relaxed">Un hébergement de qualité pour votre cheval, dans un cadre naturel et sécurisé, avec un suivi attentif au quotidien.</p>
          <div class="space-y-6 text-text/80 leading-relaxed">
            <p>Offrez à votre cheval un cadre de vie alliant confort, bien-être et sérénité au sein de notre écurie.</p>
            <p>Nous proposons une pension adaptée aux besoins des chevaux, avec une vie en groupe favorisant leur équilibre et leur sociabilité.</p>
            <p>Notre structure met à disposition des infrastructures complètes : manège, carrière, aire de douche, club house, casiers propriétaires.</p>
            <p>De nombreux chemins de balade sont accessibles directement depuis l'écurie pour profiter de moments en extérieur.</p>
            <p>La surveillance quotidienne des chevaux assure un suivi attentif et rassurant pour chaque propriétaire.</p>
          </div>
          <div class="pt-6 border-t border-secondary/20">
            <div class="grid grid-cols-4 gap-6 text-center">
              <div v-for="[val, label] in [['24h/7', 'Surveillance'], ['25', 'Boxes'], ['20', 'Hectares'], ['1', 'rond de longe']]" :key="label">
                <span class="block text-3xl font-serif font-bold text-accent mb-2">{{ val }}</span>
                <span class="text-sm font-medium text-text/70 uppercase tracking-widest">{{ label }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </AppSection>

    <!-- Atouts -->
    <AppSection title="Nos engagements" subtitle="Ce que nous offrons" variant="accent" class="relative overflow-hidden">
      <div class="absolute right-0 top-0 -translate-y-1/2 translate-x-1/3 opacity-5">
        <svg width="600" height="600" viewBox="0 0 100 100" class="text-primary fill-current"><path d="M50 0 L100 50 L50 100 L0 50 Z" /></svg>
      </div>
      <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
        <div v-for="(atout, index) in atouts" :key="index" class="text-center group">
          <div class="mx-auto w-20 h-20 rounded-2xl bg-white shadow-soft flex items-center justify-center mb-6 rotate-3 group-hover:-rotate-3 transition-transform duration-300">
            <component :is="atout.icon" class="text-primary" :size="32" />
          </div>
          <h3 class="text-xl font-serif font-bold text-primary mb-3">{{ atout.title }}</h3>
          <p class="text-text/80 leading-relaxed text-sm">{{ atout.description }}</p>
        </div>
      </div>
    </AppSection>

    <!-- Galerie -->
    <AppSection title="Nos installations" subtitle="En images" variant="default">
      <div class="grid grid-cols-2 md:grid-cols-4 gap-4 auto-rows-[200px] md:auto-rows-[250px]">
        <div v-for="(img, idx) in galerie" :key="idx" :class="`relative group overflow-hidden rounded-xl ${idx === 0 ? 'col-span-2 row-span-2' : ''}`">
          <img :src="img.src" :alt="img.alt" loading="lazy" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700" />
          <div class="absolute inset-0 bg-primary/20 group-hover:bg-transparent transition-colors duration-500 z-10" />
        </div>
      </div>
    </AppSection>

    <!-- CTA -->
    <AppSection variant="primary" class="text-white" :style="{ backgroundColor: '#41607D' }">
      <div class="max-w-4xl mx-auto text-center">
        <h2 class="text-3xl md:text-5xl font-serif font-bold mb-6">Confier votre cheval à l'Écurie Elphe</h2>
        <p class="text-xl mb-10 text-white/80 font-light">Contactez-nous pour en savoir plus sur nos formules de pension et visiter nos installations.</p>
        <div class="flex flex-col sm:flex-row justify-center items-center gap-4">
          <a href="tel:+33638101713"><AppButton variant="outline" size="lg" class="w-full sm:w-auto border-white text-white hover:bg-white/10 shadow-lg">📞 Appeler</AppButton></a>
          <NuxtLink to="/"><AppButton variant="outline" size="lg" class="w-full sm:w-auto border-white text-white hover:bg-white/10">Retour à l'accueil</AppButton></NuxtLink>
        </div>
      </div>
    </AppSection>
  </div>
</template>
