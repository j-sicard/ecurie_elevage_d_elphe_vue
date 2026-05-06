<script setup>
import { Map, Leaf, Shield, Heart } from 'lucide-vue-next'

useSeoMeta({
  title: "Balades & Randonnées | Écurie - Élevage d'Elphe",
  description: "Partez à la découverte de notre région à cheval. Balades en forêt, randonnées en pleine campagne pour tous les niveaux.",
})

const atouts = [
  { icon: Map, title: 'Itinéraires variés', description: "Des parcours adaptés à tous les niveaux, en forêt, le long des rivières ou en pleine campagne girondine. Chaque balade est une nouvelle découverte." },
  { icon: Leaf, title: 'Immersion nature', description: "Vivez une expérience unique au cœur de la nature, loin du bruit et de l'agitation. Le cheval vous invite à ralentir et à observer le monde autrement." },
  { icon: Shield, title: 'Encadrement sécurisé', description: "Toutes nos balades sont encadrées par des accompagnateurs expérimentés. Votre sécurité et votre confort sont notre priorité à chaque sortie." },
  { icon: Heart, title: 'Pour tous les niveaux', description: "Débutant ou cavalier confirmé, nous adaptons chaque sortie à votre niveau et à vos envies. Une expérience accessible à toute la famille." },
]

const galerie = [
  { src: '/images/Balade-a-cheval-riviere.jpg', alt: 'Balade à cheval en rivière' },
  { src: '/images/Champ.jpg', alt: 'Chevaux en pleine campagne' },
  { src: '/images/Gray_horse_1.jpg', alt: "Cheval gris lors d'une randonnée" },
  { src: '/images/Two_horse.jpg', alt: 'Deux cavaliers en balade' },
]
</script>

<template>
  <div>
    <!-- Hero -->
    <div class="relative h-[50vh] min-h-[400px] flex items-center justify-center overflow-hidden">
      <img src="/images/Balade-a-cheval-riviere.jpg" alt="Balade à cheval à l'Écurie Elphé" class="absolute inset-0 w-full h-full object-cover object-center" fetchpriority="high" />
      <div class="absolute inset-0 bg-primary/50 mix-blend-multiply z-10" />
      <div class="absolute inset-0 bg-gradient-to-t from-primary/70 via-transparent to-transparent z-10" />
      <div class="relative z-20 text-center text-white px-4">
        <span class="inline-block text-accent font-medium tracking-widest uppercase text-sm mb-4 drop-shadow-md">Écurie - Élevage d'Elphe</span>
        <h1 class="text-4xl md:text-6xl font-serif font-bold drop-shadow-lg">Balades & Randonnées</h1>
      </div>
    </div>

    <!-- Introduction -->
    <AppSection variant="light">
      <div class="grid md:grid-cols-2 gap-12 lg:gap-20 items-center">
        <div class="relative">
          <div class="aspect-[4/5] rounded-2xl overflow-hidden shadow-2xl relative z-10">
            <img src="/images/Balade-cariole.jpg" alt="Balade en cariole à l'Écurie Elphé" loading="lazy" class="w-full h-full object-cover" />
          </div>
          <div class="absolute top-10 -left-6 md:-left-10 w-full h-full border-4 border-accent/30 rounded-2xl -z-10" />
          <div class="absolute -bottom-8 -right-8 w-48 h-48 bg-primary/5 rounded-full blur-3xl -z-10" />
        </div>
        <div class="space-y-8">
          <span class="text-secondary font-medium tracking-wider uppercase text-sm block">Notre offre</span>
          <p class="text-xl text-primary font-serif font-medium leading-relaxed">Découvrez notre belle région girondine au rythme apaisant du pas de votre cheval.</p>
          <div class="space-y-6 text-text/80 leading-relaxed">
            <p>À l'Écurie - Élevage d'Elphe, nous vous proposons des balades et randonnées à cheval au cœur d'un cadre naturel préservé. Forêts, sentiers boisés et paysages de campagne girondine… chaque sortie est une invitation à la découverte et à la déconnexion.</p>
            <p>Que vous soyez débutant ou cavalier expérimenté, nous adaptons chaque parcours à votre niveau et à vos envies. Une expérience conviviale et ressourçante, à vivre en solo, en couple ou en famille.</p>
          </div>
          <div class="pt-6 border-t border-secondary/20">
            <div class="grid grid-cols-3 gap-6 text-center">
              <div v-for="[val, label] in [['Tous', 'Niveaux'], ['Nature', 'Girondine'], ['Famille', 'Bienvenue']]" :key="label">
                <span class="block text-3xl font-serif font-bold text-accent mb-2">{{ val }}</span>
                <span class="text-sm font-medium text-text/70 uppercase tracking-widest">{{ label }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </AppSection>

    <!-- Atouts -->
    <AppSection title="Pourquoi nous choisir" subtitle="Nos engagements" variant="accent" class="relative overflow-hidden">
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
    <AppSection title="En images" subtitle="Nos sorties" variant="default">
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
        <h2 class="text-3xl md:text-5xl font-serif font-bold mb-6">Prêt pour l'aventure ?</h2>
        <p class="text-xl mb-10 text-white/80 font-light">Contactez-nous pour réserver votre balade ou obtenir plus d'informations sur nos sorties.</p>
        <div class="flex flex-col sm:flex-row justify-center items-center gap-4">
          <a href="tel:+33638101713"><AppButton variant="outline" size="lg" class="w-full sm:w-auto border-white text-white hover:bg-white/10 shadow-lg">📞 Appeler</AppButton></a>
          <NuxtLink to="/"><AppButton variant="outline" size="lg" class="w-full sm:w-auto border-white text-white hover:bg-white/10">Retour à l'accueil</AppButton></NuxtLink>
        </div>
      </div>
    </AppSection>
  </div>
</template>
