<script setup>
const images = [
  { src: '/images/Carriere_1.jpg', alt: "Carrière équestre de l'Écurie Elphé", class: 'col-span-2 row-span-2' },
  { src: '/images/IMG_3223.jpg', alt: 'Chevaux au pré', class: 'col-span-1 row-span-1' },
  { src: '/images/IMG_3203.jpg', alt: 'Deux chevaux ensemble', class: 'col-span-1 row-span-1' },
  { src: '/images/IMG_3741.jpg', alt: 'Cheval gris en extérieur', class: 'col-span-2 row-span-1' },
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
