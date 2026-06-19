<template>
  <div class="flex flex-col items-center mb-8 md:mb-10">
    <!-- Logo circulaire -->
    <div class="relative">
      <div class="absolute inset-0 rounded-full border-2 border-accent/40 scale-110 animate-pulse" aria-hidden="true" />
      <div class="absolute inset-0 rounded-full border border-white/10 scale-105" aria-hidden="true" />
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
          src="/images/logo.jpg"
          alt="Logo Écurie - Élevage d'Elphe"
          class="w-full h-full object-contain p-2"
          loading="lazy"
        />
      </div>
    </div>

    <!-- Séparateur décoratif -->
    <div class="flex items-center justify-center gap-3 mt-8" aria-hidden="true">
      <span class="block w-10 h-px bg-accent/50" />
      <span class="block w-1.5 h-1.5 rounded-full bg-accent/70" />
      <span class="block w-10 h-px bg-accent/50" />
    </div>
  </div>
</template>
