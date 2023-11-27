<template>
    <nav class="bg-gray-800 p-4">
        <div class="flex items-center justify-between">
            <!-- Logo ou Titre -->
            <div class="flex-shrink-0">
                <router-link to="/" class="text-white font-bold text-xl">Mon Site</router-link>
            </div>

            <!-- Bouton Hamburger -->
            <button class="md:hidden" @click="toggleNav">
                <i class="fas fa-bars text-white"></i>
            </button>

            <!-- Liens de Navigation -->
            <div :class="{ 'nav-closed': !navOpen, 'nav-open': navOpen, 'md:block': true }" class="nav-menu">
                <router-link to="/" class="text-white mx-3">Accueil</router-link>
                <router-link to="/about" class="text-white mx-3">À Propos</router-link>
            </div>
        </div>
    </nav>
</template>

<script setup>
import { ref } from 'vue';
const navOpen = ref(false);

function toggleNav() {
    navOpen.value = !navOpen.value;
}
</script>

<style>
.nav-menu {
    overflow: hidden;
    transition: max-height 0.3s ease-out;
    max-height: 0;
    /* Initial state */
}

.nav-open {
    max-height: 10em;
    /* Adjust this value based on your content */
}

.nav-closed {
    max-height: 0;
}

@media (min-width: 768px) {
    .nav-menu {
        max-height: none;
    }
}
</style>
