<script setup>
import { Award, Shield, Heart, Leaf } from 'lucide-vue-next'

useSeoMeta({
  title: "École d'Équitation | Écurie - Élevage d'Elphe",
  description: "Cours d'équitation pour tous les niveaux à l'Écurie Elphé. Encadrés par un moniteur diplômé dans le respect du cheval.",
})

const atouts = [
  { icon: Award, title: 'Encadrement des cours', description: "Les cours sont assurés par un moniteur expérimenté en équitation, garantissant un enseignement progressif, sécurisé et adapté à chaque niveau." },
  { icon: Heart, title: 'Respect du cheval', description: "Notre pédagogie place le bien-être du cheval au cœur de l'apprentissage. Comprendre l'animal est la base d'une équitation juste et durable." },
  { icon: Shield, title: 'Tous niveaux', description: "Du premier contact avec le cheval jusqu'au perfectionnement, nous adaptons chaque cours à votre niveau, votre rythme et vos objectifs." },
  { icon: Leaf, title: 'Cadre naturel', description: "Nos carrières et nos paddocks sont entretenus avec soin pour offrir les meilleures conditions d'apprentissage, en toute sécurité." },
]

const galerie = [
  { src: '/images/IMG_3203.jpg', alt: "Carrière équestre de l'Écurie Elphe" },
  { src: '/images/IMG_6774.jpg', alt: "Rond de longe de l'Écurie Elphe." },
  { src: '/images/1C0DB5CA-7527-48B4-92A8-2F4E651A8041.PNG', alt: "Cours d'équitation de nuit de l'écurie d'Elphe" },
  { src: '/images/IMG_3736.jpg', alt: "Manège de l'écurie d'Elphe" },
]
</script>

<template>
  <div>
    <!-- Hero -->
    <div class="relative h-[50vh] min-h-[400px] flex items-center justify-center overflow-hidden">
      <img src="/images/Carriere_1.jpg" alt="École d'équitation à l'Écurie Elphé" class="absolute inset-0 w-full h-full object-cover object-center" fetchpriority="high" />
      <div class="absolute inset-0 bg-primary/50 mix-blend-multiply z-10" />
      <div class="absolute inset-0 bg-gradient-to-t from-primary/70 via-transparent to-transparent z-10" />
      <div class="relative z-20 text-center text-white px-4">
        <span class="inline-block text-accent font-medium tracking-widest uppercase text-sm mb-4 drop-shadow-md">Écurie - Élevage d'Elphe</span>
        <h1 class="text-4xl md:text-6xl font-serif font-bold drop-shadow-lg">École d'Équitation</h1>
      </div>
    </div>

    <!-- Introduction -->
    <AppSection variant="light">
      <div class="grid md:grid-cols-2 gap-12 lg:gap-20 items-center">
        <div class="relative">
          <div class="aspect-[4/5] rounded-2xl overflow-hidden shadow-2xl relative z-10">
            <img src="/images/Carriere_2.jpg" alt="Cavalière en cours d'équitation" loading="lazy" class="w-full h-full object-cover" />
          </div>
          <div class="absolute top-10 -left-6 md:-left-10 w-full h-full border-4 border-accent/30 rounded-2xl -z-10" />
          <div class="absolute -bottom-8 -right-8 w-48 h-48 bg-primary/5 rounded-full blur-3xl -z-10" />
        </div>
        <div class="space-y-8">
          <span class="text-secondary font-medium tracking-wider uppercase text-sm block">Notre pédagogie</span>
          <p class="text-xl text-primary font-serif font-medium leading-relaxed">Une approche bienveillante et structurée, centrée sur la progression de chaque cavalier et le respect de l'animal.</p>
          <div class="space-y-6 text-text/80 leading-relaxed">
            <p>Des cours adaptés à chaque niveau, avec une cavalerie douce et fiable, idéale pour apprendre en confiance.</p>
            <p>Enfants, adolescents et adultes, du débutant au confirmé, trouvent des créneaux qui leur sont dédiés.</p>
            <p>Chaque équidé dispose de son propre matériel, pour garantir confort et bien-être.</p>
            <p>Nous proposons une équitation de loisir, sans renoncer à la recherche d'une équitation de qualité. Toutes les disciplines sont abordées dans un esprit d'ouverture et de progression, sans objectif de compétition.</p>
          </div>
          <div class="pt-6 border-t border-secondary/20">
            <div class="grid grid-cols-4 gap-6 text-center">
              <div v-for="[val, label] in [['Tous', 'Niveaux'], ['1', 'Carrière'], ['1', 'Manège'], ['1', 'rond de long']]" :key="label">
                <span class="block text-3xl font-serif font-bold text-accent mb-2">{{ val }}</span>
                <span class="text-sm font-medium text-text/70 uppercase tracking-widest">{{ label }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </AppSection>

    <!-- Atouts -->
    <AppSection title="Notre approche" subtitle="Ce qui nous distingue" variant="accent" class="relative overflow-hidden">
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
    <AppSection variant="primary" class="text-white" :style="{ backgroundColor: '#1953f3ff' }">
      <div class="max-w-4xl mx-auto text-center">
        <h2 class="text-3xl md:text-5xl font-serif font-bold mb-6">Prêt à monter en selle ?</h2>
        <p class="text-xl mb-10 text-white/80 font-light">Contactez-nous pour vous inscrire à un cours d'essai ou obtenir plus d'informations sur nos formules.</p>
        <div class="flex flex-col sm:flex-row justify-center items-center gap-4">
          <a href="tel:+33638101713"><AppButton variant="outline" size="lg" class="w-full sm:w-auto border-white text-white hover:bg-white/10 shadow-lg">📞 Appeler</AppButton></a>
          <NuxtLink to="/"><AppButton variant="outline" size="lg" class="w-full sm:w-auto border-white text-white hover:bg-white/10">Retour à l'accueil</AppButton></NuxtLink>
        </div>
      </div>
    </AppSection>
  </div>
</template>
