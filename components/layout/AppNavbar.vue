<script setup>
import { Menu, X } from 'lucide-vue-next'

const route = useRoute()
const hasHero = computed(() => route.path === '/')

const isScrolled = ref(!hasHero.value)
const isOpen = ref(false)

const navLinks = [
  { name: 'Accueil', href: '/#home' },
  { name: 'Le Domaine', href: '/#about' },
  { name: 'Services', href: '/#services' },
  { name: 'Galerie', href: '/#gallery' },
]

onMounted(() => {
  if (!hasHero.value) {
    isScrolled.value = true
    return
  }
  const handleScroll = () => {
    isScrolled.value = window.scrollY > 20
  }
  window.addEventListener('scroll', handleScroll)
  onUnmounted(() => window.removeEventListener('scroll', handleScroll))
})

const navClass = computed(() =>
  `fixed top-0 w-full z-50 transition-all duration-300 ${
    isScrolled.value
      ? 'bg-background/95 backdrop-blur-md shadow-soft py-4'
      : 'bg-transparent py-6'
  }`
)

const logoClass = computed(() =>
  `text-2xl font-serif font-bold flex-shrink-0 ${
    isScrolled.value ? 'text-white' : 'text-white sm:text-white'
  }`
)

const linkClass = computed(() =>
  `text-sm font-medium hover:text-accent transition-colors ${
    isScrolled.value ? 'text-text' : 'text-text sm:text-white/90 sm:hover:text-white'
  }`
)
</script>

<template>
  <nav :class="navClass">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center">
        <a href="/#home" :class="logoClass">
          Écurie - Élevage d'Elphe 
        </a>

        <!-- Desktop -->
        <div class="hidden md:flex items-center space-x-8">
          <ul class="flex space-x-8">
            <li v-for="link in navLinks" :key="link.name">
              <a :href="link.href" :class="linkClass">{{ link.name }}</a>
            </li>
          </ul>
          <a href="/#contact">
            <AppButton variant="primary" size="sm" class="hidden lg:inline-flex">
              Nous contacter
            </AppButton>
          </a>
        </div>

        <!-- Mobile toggle -->
        <button
          class="md:hidden text-primary"
          :aria-label="isOpen ? 'Fermer le menu' : 'Ouvrir le menu'"
          @click="isOpen = !isOpen"
        >
          <X v-if="isOpen" :size="24" />
          <Menu v-else :size="24" />
        </button>
      </div>
    </div>

    <!-- Mobile menu -->
    <div v-if="isOpen" class="md:hidden bg-background absolute top-full left-0 w-full shadow-lg border-t border-secondary/10">
      <ul class="px-4 py-6 space-y-4">
        <li v-for="link in navLinks" :key="link.name">
          <a :href="link.href" class="block text-lg font-medium text-text hover:text-primary transition-colors" @click="isOpen = false">
            {{ link.name }}
          </a>
        </li>
        <li class="pt-4">
          <a href="/#contact" @click="isOpen = false">
            <AppButton variant="primary" class="w-full">Nous contacter</AppButton>
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>
