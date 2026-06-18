<script setup>
const services = [
  {
    title: "École d'Équitation",
    description: "Des cours d'équitation adaptés à tous les niveaux, encadrés par un moniteur diplômé, dans une approche respectueuse du cheval et centrée sur la progression de chacun.",
    image: '/images/Carriere_1.jpg',
    href: '/equitation',
  },
  {
    title: "Pension pour chevaux",
    description: "Des formules de pension au pré, en paddock ou en box, avec sorties quotidiennes. Surveillance 24h/7 et foin à volonté.",
    image: '/images/Champ.jpg',
    href: '/pension',
  }, 
  {
    title: "Élevage",
    description: "Un élevage familial sélectionné pour le mental et le sport. Nous vous accompagnons dans le choix de votre futur partenaire.",
    image: '/images/Horse_group.jpg',
    href: '/elevage',
  },
  {
    title: "Boutique & Sellerie",
    description: "Découvrez notre boutique aux couleurs du club : \n t-shirts, sweats, casquettes et plus encore. Retrouvez aussi notre sellerie en ligne pour vos achats utiles. Merci pour votre soutien !",
    image: '/images/logo_shop.png',
    href: 'https://blagapro.com/categorie-produit/boutiques-des-clubs/nouvelle-aquitaine/gironde-33/ecurie-elevage-delphe-33390/',
  },
]
</script>

<template>
  <AppSection id="services" title="Nos Activités" subtitle="Ce que nous proposons" variant="default">
    <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
      <AppCard
        v-for="(service, index) in services"
        :key="index"
        v-bind="service"
        class="h-full flex flex-col"
      />
    </div>
  </AppSection>
</template>
