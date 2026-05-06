<script setup>
const props = defineProps({
  variant: {
    type: String,
    default: 'primary',
  },
  size: {
    type: String,
    default: 'md',
  },
  class: {
    type: String,
    default: '',
  },
})

const base = 'inline-flex items-center justify-center rounded-md font-medium transition-colors focus:outline-none focus:ring-2 focus:ring-primary/50'

const variants = {
  primary: 'bg-primary text-white hover:bg-primary/90',
  secondary: 'bg-secondary text-white hover:bg-secondary/90',
  outline: 'border-2 border-primary text-primary hover:bg-primary/5',
  ghost: 'text-primary hover:bg-primary/10',
}

const sizes = {
  sm: 'h-9 px-4 text-sm',
  md: 'h-11 px-6 text-base',
  lg: 'h-14 px-8 text-lg',
}

const classes = computed(() =>
  `${base} ${variants[props.variant]} ${sizes[props.size]} ${props.class}`
)
</script>

<template>
  <button :class="classes">
    <slot />
  </button>
</template>
