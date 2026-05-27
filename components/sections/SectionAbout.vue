<template>
  <AppSection id="about" title="Notre Domaine" subtitle="L'esprit de l'Écurie Elphe" variant="light">
    <div class="grid md:grid-cols-2 gap-12 lg:gap-20 items-center">
      <div class="order-2 md:order-1 relative">
        <div class="aspect-[4/5] rounded-2xl overflow-hidden shadow-2xl relative z-10">
          <img src="/images/Head_Horse.jpg" alt="Cavalière au sein du domaine" loading="lazy" class="w-full h-full object-cover" />
        </div>
        <div class="absolute top-10 -left-6 md:-left-10 w-full h-full border-4 border-accent/30 rounded-2xl -z-10" />
        <div class="absolute -bottom-8 -right-8 w-48 h-48 bg-primary/5 rounded-full blur-3xl -z-10" />
      </div>

      <div class="order-1 md:order-2 space-y-8">
        <p class="text-xl text-primary font-serif font-medium leading-relaxed">
          Située dans un cadre verdoyant et paisible, notre écurie offre à vos chevaux des conditions de vie optimales, proches de leurs besoins naturels.
        </p>
        <div class="space-y-6 text-text/80 leading-relaxed">
          <p>Fondée sur la passion de l'élevage et le respect de l'animal, l'Écurie Elphe est bien plus qu'un centre équestre. C'est un lieu de vie où se créent des liens uniques entre l'homme et sa monture.</p>
          <p>Que vous soyez cavalier débutant cherchant à découvrir le monde du cheval, ou propriétaire exigeant à la recherche d'une pension de qualité, notre équipe vous accompagne avec bienveillance.</p>
        </div>
        <div class="pt-6 border-t border-secondary/20">
          <div class="grid grid-cols-2 sm:grid-cols-5 gap-6 text-center">
            <div v-for="[val, label] in [['20', 'Hectares'], ['25', 'Boxes'], ['1', 'Carrière'], ['1', 'Manège'], ['1', 'rond de longe']]" :key="label">
              <span class="block text-3xl font-serif font-bold text-accent mb-2">{{ val }}</span>
              <span class="text-sm font-medium text-text/70 uppercase tracking-widest">{{ label }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </AppSection>
</template>
