# Écurie - Élevage d'Elphe — Version Nuxt 3

Version Vue 3 / Nuxt 3 SSG du site Écurie - Élevage d'Elphe.
Reproduction pixel-perfect de la version React/Next.js.

## Stack

- **Nuxt 3** — App Router, SSG (`nuxi generate`)
- **Vue 3** — `<script setup>` Composition API
- **Tailwind CSS v3** — design system identique à la version React
- **lucide-vue-next** — icônes

## Structure

```
nuxt-version/
├── app.vue
├── nuxt.config.ts
├── tailwind.config.js
├── assets/css/globals.css
├── layouts/default.vue
├── pages/
│   ├── index.vue
│   ├── elevage.vue
│   ├── balades.vue
│   ├── equitation.vue
│   ├── pension.vue
│   ├── mentions-legales.vue
│   └── politique-confidentialite.vue
└── components/
    ├── layout/
    │   ├── AppNavbar.vue
    │   └── AppFooter.vue
    ├── sections/
    │   ├── SectionHero.vue
    │   ├── SectionAbout.vue
    │   ├── SectionServices.vue
    │   ├── SectionValues.vue
    │   ├── SectionGallery.vue
    │   └── SectionContactCTA.vue
    └── ui/
        ├── AppButton.vue
        ├── AppSection.vue
        └── AppCard.vue
```

## Images

Copier les images depuis `../src/assets/` vers `public/images/` :

```bash
cp ../src/assets/*.jpg public/images/
```

## Démarrage

```bash
npm install
npm run dev        # développement → http://localhost:3000
npm run build      # génère dist/ (fichiers statiques)
```

## Déploiement

Le dossier `dist/` généré par `npm run build` est déployable sur
Netlify, Vercel (static), GitHub Pages ou tout hébergeur statique.
