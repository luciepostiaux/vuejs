<script setup>
import ButtonComponent from './../components/ButtonComponent.vue'
import TitleComponent from './../components/TitleComponent.vue';
import ContactFormComponent from '../components/ContactFormComponent.vue';


</script>

<template class="dark">
  <header>
  </header>
  <main>
    <ButtonComponent text="Click Me" type="primary" @click="handleClick" />
    <ButtonComponent text="Click Me" type="secondary" @click="handleClick" />
    <ButtonComponent text="Danger" type="danger" />

     <div>
      <TitleComponent level="h1">Titre de niveau 1</TitleComponent>
      <TitleComponent level="h2">Titre de niveau 2</TitleComponent>
      <TitleComponent level="h3">Titre de niveau 3</TitleComponent>
    </div>

         <div>
          <ContactFormComponent/>
      </div>

    <RouterView />
  </main>
</template>