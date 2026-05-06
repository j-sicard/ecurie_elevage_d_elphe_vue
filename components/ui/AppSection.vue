<script setup>
const props = defineProps({
  id: String,
  title: String,
  subtitle: String,
  variant: {
    type: String,
    default: 'default',
  },
  class: {
    type: String,
    default: '',
  },
  style: {
    type: Object,
    default: () => ({}),
  },
})

const variants = {
  default: 'bg-background',
  light: 'bg-white',
  accent: 'bg-accent/5',
  primary: 'bg-primary',
}

const sectionClass = computed(() =>
  `py-20 md:py-28 ${variants[props.variant]} ${props.class}`
)
</script>

<template>
  <section :id="id" :class="sectionClass" :style="style">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div v-if="title || subtitle" class="text-center max-w-3xl mx-auto mb-16">
        <span v-if="subtitle" class="text-secondary font-medium tracking-wider uppercase text-sm mb-3 block">
          {{ subtitle }}
        </span>
        <h2 v-if="title" class="text-3xl md:text-4xl lg:text-5xl font-bold">
          {{ title }}
        </h2>
      </div>
      <slot />
    </div>
  </section>
</template>
