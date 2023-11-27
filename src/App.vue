<script setup>
import { RouterView } from "vue-router";
import NavBar from "./components/NavbarComponent.vue";
import AutocompleteSelectComponent from "./components/AutocompleteSelectComponent.vue";
</script>

<template>
  <header>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" rel="stylesheet">

    <NavBar />
    <AutocompleteSelectComponent/>
  </header>

  <RouterView />
</template>
