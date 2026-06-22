<template>
  <AppSection id="contact" variant="primary" class="text-white" :style="{ backgroundColor: '#0b044eff' }">
    <div class="max-w-4xl mx-auto text-center">

      <!-- Logo circulaire -->
      <div class="flex justify-center mb-8 md:mb-10">
        <div class="relative">
          <!-- Anneau décoratif externe -->
          <div class="absolute inset-0 rounded-full border-2 border-accent/40 scale-110 animate-pulse" aria-hidden="true" />
          <!-- Anneau intermédiaire -->
          <div class="absolute inset-0 rounded-full border border-white/10 scale-105" aria-hidden="true" />
          <!-- Cercle logo -->
          <div class="
            w-32 h-32
            sm:w-36 sm:h-36
            md:w-44 md:h-44
            rounded-full overflow-hidden
            ring-2 ring-accent/60
            shadow-[0_0_40px_rgba(196,164,132,0.25)]
            bg-white
            transition-transform duration-500 hover:scale-105
          ">
            <img
              src="/images/logo-ecurie-elevage-elphe.jpg"
              alt="Logo Écurie - Élevage d'Elphe"
              class="w-full h-full object-contain p-2"
              loading="lazy"
            />
          </div>
        </div>
      </div>

      <!-- Séparateur décoratif -->
      <div class="flex items-center justify-center gap-3 mb-6" aria-hidden="true">
        <span class="block w-10 h-px bg-accent/50" />
        <span class="block w-1.5 h-1.5 rounded-full bg-accent/70" />
        <span class="block w-10 h-px bg-accent/50" />
      </div>

      <h2 class="text-3xl md:text-5xl font-serif font-bold mb-6">
        Prêt à nous rejoindre ?
      </h2>
      <p class="text-xl mb-10 text-white/80 font-light">
        Venez découvrir notre domaine et partager notre passion du cheval. Contactez-nous par téléphone ou par SMS.
      </p>
      <div class="flex flex-col sm:flex-row justify-center items-center gap-4">
        <a href="tel:+33638101713">
          <AppButton variant="outline" size="lg" class="w-full sm:w-auto border-white text-white hover:bg-white/10 shadow-lg">
            📞 Appeler
          </AppButton>
        </a>
        <a href="sms:+33638101713">
          <AppButton variant="outline" size="lg" class="w-full sm:w-auto border-white text-white hover:bg-white/10">
            💬 Envoyer un SMS
          </AppButton>
        </a>
      </div>
    </div>
  </AppSection>
</template>
