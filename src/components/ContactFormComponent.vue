<template>
    <div>
        <form @submit.prevent="submitForm">
            <div>
                <label for="name">Nom:</label>
                <input type="text" id="name" v-model="form.name">
            </div>
            <div>
                <label for="email">Email:</label>
                <input type="email" id="email" v-model="form.email">
            </div>
            <div>
                <label for="subject">Sujet:</label>
                <input type="text" id="subject" v-model="form.subject">
            </div>
            <div>
                <label for="message">Message:</label>
                <textarea id="message" v-model="form.message"></textarea>
            </div>
            <button type="submit">Envoyer</button>
        </form>

        <div v-if="submitted">
            <h3>Données Soumises :</h3>
            <p>Nom: {{ form.name }}</p>
            <p>Email: {{ form.email }}</p>
            <p>Sujet: {{ form.subject }}</p>
            <p>Message: {{ form.message }}</p>
        </div>
    </div>
</template>

<script setup>
import { reactive, ref } from 'vue';

const form = reactive({
    name: '',
    email: '',
    subject: '',
    message: ''
});

const submitted = ref(false);

function submitForm() {
    submitted.value = true;
}
</script>

<style>
/* Ajoutez ici le style de votre choix */
</style>
