<template>
  <AppSection id="contact" variant="primary" class="text-white" :style="{ backgroundColor: '#1953f3ff' }">
    <div class="max-w-4xl mx-auto text-center">
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
