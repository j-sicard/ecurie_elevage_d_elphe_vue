<script setup>
import { MapPin, Phone } from 'lucide-vue-next'

const year = new Date().getFullYear()
</script>

<template>
  <footer class="text-white/80 pt-20 pb-10" style="background-color: #41607D">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-12 mb-16">

        <div class="lg:col-span-1">
          <h3 class="text-2xl font-serif font-bold text-white mb-6">Écurie - Élevage d'Elphe</h3>
          <p class="leading-relaxed">
            Un écrin de nature dédié à la passion du cheval. Pension, élevage et enseignement dans le plus grand respect de l'animal.
          </p>
        </div>

        <div>
          <h4 class="text-lg font-bold text-white mb-6">Navigation</h4>
          <ul class="space-y-4">
            <li><a href="/#home" class="hover:text-white transition-colors">Accueil</a></li>
            <li><a href="/#about" class="hover:text-white transition-colors">Le Domaine</a></li>
            <li><a href="/#services" class="hover:text-white transition-colors">Nos Services</a></li>
            <li><a href="/#gallery" class="hover:text-white transition-colors">Galerie Photo</a></li>
          </ul>
        </div>

        <div>
          <h4 class="text-lg font-bold text-white mb-6">Les Activités</h4>
          <ul class="space-y-4">
            <li><NuxtLink to="/equitation" class="hover:text-white transition-colors">Cours d'équitation</NuxtLink></li>
            <li><NuxtLink to="/balades" class="hover:text-white transition-colors">Balades & Randonnées</NuxtLink></li>
            <li><NuxtLink to="/pension" class="hover:text-white transition-colors">Pension Paddock/Box</NuxtLink></li>
            <li><NuxtLink to="/elevage" class="hover:text-white transition-colors">Élevage & Vente</NuxtLink></li>
          </ul>
        </div>

        <div>
          <h4 class="text-lg font-bold text-white mb-6">Contact</h4>
          <ul class="space-y-4">
            <li class="flex items-start">
              <MapPin class="mr-3 flex-shrink-0 text-accent/80" :size="20" aria-hidden="true" />
              <span>Centre Équestre, 17 Route du Lion d'Or, 33390 Cartelegue</span>
            </li>
            <li class="flex items-center">
              <Phone class="mr-3 flex-shrink-0 text-accent/80" :size="20" aria-hidden="true" />
              <a href="tel:+33638101713" class="hover:text-white transition-colors">06 38 10 17 13</a>
            </li>
            <li class="flex items-center">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="mr-3 flex-shrink-0 text-accent/80" aria-hidden="true">
                <path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"/>
              </svg>
              <a href="https://www.facebook.com/p/%C3%89curie-%C3%89levage-dElphe-61571794096499/" target="_blank" rel="noopener noreferrer" class="hover:text-white transition-colors">Notre page Facebook</a>
            </li>
          </ul>
        </div>

      </div>

      <div class="border-t border-white/10 pt-8 flex flex-col md:flex-row justify-between items-center text-sm text-white/70">
        <p>© {{ year }} Écurie - Élevage d'Elphe. Tous droits réservés.</p>
        <div class="flex space-x-6 mt-4 md:mt-0">
          <NuxtLink to="/mentions-legales" class="hover:text-white transition-colors underline underline-offset-2">Mentions Légales</NuxtLink>
          <NuxtLink to="/politique-confidentialite" class="hover:text-white transition-colors underline underline-offset-2">Politique de confidentialité</NuxtLink>
        </div>
      </div>
    </div>
  </footer>
</template>
