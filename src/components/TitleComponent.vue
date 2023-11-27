<script>
export default {
  props: {
    level: {
      type: String,
      default: "h1", // Niveau de titre par défaut
    },
  },
  methods: {
    getTitleStyle() {
      // Utilise les différentes classes TailwindCSS en fonction du niveau de titre
      switch (this.level) {
        case "h1":
          return "text-4xl font-bold";
        case "h2":
          return "text-3xl font-bold";
        case "h3":
          return "text-2xl font-bold";
        // Ajoute d'autres cas pour d'autres niveaux de titre si nécessaire
        default:
          return "text-4xl font-bold";
      }
    },
  },
};
</script>

<template>
  <div :class="getTitleStyle()">
    <slot></slot>
  </div>
</template>
