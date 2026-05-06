<script setup>
const props = defineProps({
  title: String,
  description: String,
  image: String,
  href: String,
  class: {
    type: String,
    default: '',
  },
})
</script>

<template>
  <NuxtLink v-if="href" :to="href" class="block h-full">
    <div :class="`group bg-white rounded-xl overflow-hidden shadow-soft hover:shadow-md transition-all duration-300 border border-secondary/10 cursor-pointer ${props.class}`">
      <div v-if="image" class="aspect-[4/3] overflow-hidden relative">
        <img :src="image" :alt="title" loading="lazy" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
      </div>
      <div class="p-6 md:p-8">
        <h3 class="text-xl font-bold mb-3">{{ title }}</h3>
        <p class="text-text/80 leading-relaxed">{{ description }}</p>
        <span class="inline-block mt-4 text-sm font-medium text-primary group-hover:text-accent transition-colors">
          En savoir plus →
        </span>
      </div>
    </div>
  </NuxtLink>
  <div v-else :class="`group bg-white rounded-xl overflow-hidden shadow-soft hover:shadow-md transition-all duration-300 border border-secondary/10 ${props.class}`">
    <div v-if="image" class="aspect-[4/3] overflow-hidden relative">
      <img :src="image" :alt="title" loading="lazy" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
    </div>
    <div class="p-6 md:p-8">
      <h3 class="text-xl font-bold mb-3">{{ title }}</h3>
      <p class="text-text/80 leading-relaxed">{{ description }}</p>
    </div>
  </div>
</template>
