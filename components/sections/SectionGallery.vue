<script setup>
const images = [
  { src: '/images/carriere-equestre-boxes-ecurie-elevage-elphe.jpg', alt: "Carrière équestre de l'Écurie élevage d'Elphe.", class: 'col-span-2 row-span-2' },
  { src: '/images/boxes-ecurie-elevage-elphe.jpg', alt: "Boxes a cheval de l'écurie - élevage d'elphe.", class: 'col-span-1 row-span-1' },
  { src: '/images/carriere-equestre-ecurie-elevage-elphe.jpg', alt: "Carrière de l'écurie - élevage d'elphe.", class: 'col-span-1 row-span-1' },
  { src: '/images/boxes-vu-aerienne-ecurie-elevage-elphe.jpg', alt: "Vu aérienne des boxes de l'écurie - élevage d'eplhe.", class: 'col-span-2 row-span-1' },
]
</script>

<template>
  <AppSection id="gallery" title="Galerie Photo" subtitle="En images" variant="default">
    <div class="grid grid-cols-2 md:grid-cols-4 gap-4 auto-rows-[200px] md:auto-rows-[250px]">
      <div
        v-for="(img, idx) in images"
        :key="idx"
        :class="`relative group overflow-hidden rounded-xl ${img.class}`"
      >
        <img
          :src="img.src"
          :alt="img.alt"
          loading="lazy"
          class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700"
        />
        <div class="absolute inset-0 bg-primary/20 group-hover:bg-transparent transition-colors duration-500 z-10" />
      </div>
    </div>
  </AppSection>
</template>
