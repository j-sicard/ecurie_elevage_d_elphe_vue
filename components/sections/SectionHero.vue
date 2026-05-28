<script setup>
import { ArrowDown } from 'lucide-vue-next'
</script>

<template>
  <div id="home" class="relative h-screen min-h-[600px] flex items-center justify-center overflow-hidden">
    <img
      src="/images/IMG_9604.jpg"
      alt=""
      class="absolute inset-0 w-full h-full object-cover object-[center_10%]"
      fetchpriority="high"
    />
    <div class="absolute inset-0 bg-primary/40 mix-blend-multiply z-10" />
    <div class="absolute inset-0 bg-gradient-to-t from-primary/80 via-transparent to-transparent z-10" />

    <div class="relative z-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center text-white mt-16">
      <span class="inline-block text-accent font-medium tracking-widest uppercase text-sm mb-6 drop-shadow-md">
        Nature, Passion & Transmission
      </span>
      <h1 class="text-5xl md:text-7xl lg:text-8xl font-serif font-bold mb-8 leading-tight drop-shadow-lg">
        Écurie - Élevage<br />
        <span class="text-white/90 italic">d'Elphe</span>
      </h1>
      <p class="text-lg md:text-xl font-light mb-12 max-w-2xl mx-auto opacity-90 leading-relaxed drop-shadow-md">
        Bienvenue dans notre domaine, où la rigueur guide chaque geste et où le respect est partagé par tous, humains comme chevaux.
        Un lieu structuré par des codes et des règles, garants d'une vie en communauté harmonieuse, sécurisée et tournée vers le bien-être et la progression de chacun.
      </p>
      <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
        <a href="#services">
          <AppButton variant="primary" size="lg" class="w-full sm:w-auto shadow-lg hover:shadow-xl hover:-translate-y-0.5 transition-all">
            Découvrir nos activités
          </AppButton>
        </a>
        <a href="#about">
          <AppButton variant="outline" size="lg" class="w-full sm:w-auto text-white border-white hover:bg-white/10 backdrop-blur-sm">
            Visiter le domaine
          </AppButton>
        </a>
      </div>
    </div>

    <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 z-20 animate-bounce">
      <a href="#about" class="text-white/70 hover:text-white transition-colors">
        <ArrowDown :size="32" />
      </a>
    </div>
  </div>
</template>
