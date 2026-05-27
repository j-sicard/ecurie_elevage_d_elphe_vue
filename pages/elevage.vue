<script setup>
import { Heart, Leaf, Shield, Award } from 'lucide-vue-next'

useSeoMeta({
  title: "Élevage | Écurie - Élevage d'Elphe",
  description: "Découvrez notre élevage familial de chevaux sélectionnés pour le mental et le sport.",
})

const valeurs = [
  {
    icon: Heart,
    title: 'Sélection rigoureuse',
    description: "Nous privilégions des étalons et juments au caractère sain, gentil et polyvalent afin que les poulains conviennent à une grande diversité de cavaliers.",
  },
  {
    icon: Leaf,
    title: 'Élevage naturel',
    description: "Nos chevaux grandissent en liberté, en troupeau, avec un accès permanent aux pâtures. Cette approche favorise leur développement physique et psychologique.",
  }, 
  {
    icon: Award,
    title: 'Accompagnement personnalisé',
    description: "Nous vous guidons dans le choix de votre futur partenaire selon votre niveau, vos objectifs et votre sensibilité. Une relation de confiance durable.",
  },
]

const galerie = [
  { src: '/images/Horse_group.jpg', alt: "Groupe de chevaux de l'élevage" },
  { src: '/images/Gray_horse_1.jpg', alt: "Cheval gris de l'élevage" },
  { src: '/images/White_horse.jpg', alt: "Cheval blanc de l'élevage" },
  { src: '/images/Two_horse.jpg', alt: 'Deux chevaux ensemble' },
]
</script>

<template>
  <div>
    <!-- Hero -->
    <div class="relative h-[50vh] min-h-[400px] flex items-center justify-center overflow-hidden">
      <img src="/images/Horse_group.jpg" alt="Élevage de l'Écurie Elphe" class="absolute inset-0 w-full h-full object-cover object-center" fetchpriority="high" />
      <div class="absolute inset-0 bg-primary/50 mix-blend-multiply z-10" />
      <div class="absolute inset-0 bg-gradient-to-t from-primary/70 via-transparent to-transparent z-10" />
      <div class="relative z-20 text-center text-white px-4">
        <span class="inline-block text-accent font-medium tracking-widest uppercase text-sm mb-4 drop-shadow-md">Écurie - Élevage d'Elphe</span>
        <h1 class="text-4xl md:text-6xl font-serif font-bold drop-shadow-lg">Notre Élevage</h1>
      </div>
    </div>

    <!-- Introduction -->
    <AppSection variant="light">
      <div class="grid md:grid-cols-2 gap-12 lg:gap-20 items-center">
        <div class="relative">
          <div class="aspect-[4/5] rounded-2xl overflow-hidden shadow-2xl relative z-10">
            <img src="/images/Gray_horse_1.jpg" alt="Cheval de l'élevage Elphe" loading="lazy" class="w-full h-full object-cover" />
          </div>
          <div class="absolute top-10 -left-6 md:-left-10 w-full h-full border-4 border-accent/30 rounded-2xl -z-10" />
          <div class="absolute -bottom-8 -right-8 w-48 h-48 bg-primary/5 rounded-full blur-3xl -z-10" />
        </div>
        <div class="space-y-8">
          <span class="text-secondary font-medium tracking-wider uppercase text-sm block">Notre philosophie</span>
          <p class="text-xl text-primary font-serif font-medium leading-relaxed">
            Un élevage familial fondé sur le respect du cheval, la passion et le bien-être au cœur de chaque naissance.
          </p>
          <div class="space-y-6 text-text/80 leading-relaxed">
            <p>Notre élevage s'articule autour de deux étalons : un fjord PP gris souris (grullo) et un WPB crémello.</p>
            <p>Ils vivent au pré toute l'année, aux côtés de leurs juments et de leurs poulains, participant naturellement à leur éducation dans un cadre respectueux de leurs besoins et de leur vie en troupeau.</p>
            <p>La sélection repose sur le mental et la morphologie de nos chevaux. L'objectif est de faire naître des chevaux bien dans leur tête, proches de l'humain et adaptés à une équitation de loisir.</p>
            <p>Les poulains produits sont d'origines constatées. Ils sont sevrés au rythme de leurs besoins et de ceux des juments.</p>
            <p>Ils sont sociabilisés en douceur. Avant leur départ, ils sont manipulés avec soin et apprennent les bases : marche en main, tenir à l'attache, donner les pieds.</p>
            <p>Ils sont également habitués à la vie en écurie (box, respect des clôtures électriques, présence de chiens, chats, poules, bruit de tracteurs, enfants…).</p>
          </div>
          <div class="pt-6 border-t border-secondary/20">
            <div class="grid grid-cols-3 gap-6 text-center">
              <div v-for="[val, label] in [['100%', 'Élevage naturel'], ['20', 'Hectares'], ['♥', 'Passion']]" :key="label">
                <span class="block text-3xl font-serif font-bold text-accent mb-2">{{ val }}</span>
                <span class="text-sm font-medium text-text/70 uppercase tracking-widest">{{ label }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </AppSection>

    <!-- Valeurs -->
    <AppSection title="Notre approche" subtitle="Ce qui nous distingue" variant="accent" class="relative overflow-hidden">
      <div class="absolute right-0 top-0 -translate-y-1/2 translate-x-1/3 opacity-5">
        <svg width="600" height="600" viewBox="0 0 100 100" class="text-primary fill-current"><path d="M50 0 L100 50 L50 100 L0 50 Z" /></svg>
      </div>
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="(valeur, index) in valeurs" :key="index" class="text-center group">
          <div class="mx-auto w-20 h-20 rounded-2xl bg-white shadow-soft flex items-center justify-center mb-6 rotate-3 group-hover:-rotate-3 transition-transform duration-300">
            <component :is="valeur.icon" class="text-primary" :size="32" />
          </div>
          <h3 class="text-xl font-serif font-bold text-primary mb-3">{{ valeur.title }}</h3>
          <p class="text-text/80 leading-relaxed text-sm">{{ valeur.description }}</p>
        </div>
      </div>
    </AppSection>

    <!-- Galerie -->
    <AppSection title="Nos chevaux" subtitle="En images" variant="default">
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
        <h2 class="text-3xl md:text-5xl font-serif font-bold mb-6">Intéressé par nos chevaux ?</h2>
        <p class="text-xl mb-10 text-white/80 font-light">Contactez-nous pour en savoir plus sur nos poulains disponibles ou pour visiter notre élevage.</p>
        <div class="flex flex-col sm:flex-row justify-center items-center gap-4">
          <a href="tel:+33638101713"><AppButton variant="outline" size="lg" class="w-full sm:w-auto border-white text-white hover:bg-white/10 shadow-lg">📞 Appeler</AppButton></a>
          <NuxtLink to="/"><AppButton variant="outline" size="lg" class="w-full sm:w-auto border-white text-white hover:bg-white/10">Retour à l'accueil</AppButton></NuxtLink>
        </div>
      </div>
    </AppSection>
  </div>
</template>
