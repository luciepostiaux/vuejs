<template>
    <div class="autocomplete">
        <input type="text" v-model="search" @input="filterOptions" placeholder="Tapez pour rechercher..." />

        <ul v-if="filteredOptions.length" class="autocomplete-results">
            <li v-for="option in filteredOptions" :key="option.nom" @click="selectOption(option)">
                {{ option.prenom }} {{ option.nom }}
            </li>
        </ul>
    </div>
</template>


<script>
const noms = [{ 'nom': 'Dupont', 'prenom': 'Ivan' }, { 'nom': 'Leroy', 'prenom': 'Julia' }, { 'nom': 'Laurent', 'prenom': 'Bob' }, { 'nom': 'Leroy', 'prenom': 'Fiona' }, { 'nom': 'Laurent', 'prenom': 'Emma' }, { 'nom': 'Durand', 'prenom': 'Emma' }, { 'nom': 'Petit', 'prenom': 'Fiona' }, { 'nom': 'Michel', 'prenom': 'Alice' }, { 'nom': 'Simon', 'prenom': 'Emma' }, { 'nom': 'Martin', 'prenom': 'Alice' }, { 'nom': 'Lefebvre', 'prenom': 'Alice' }, { 'nom': 'Michel', 'prenom': 'Ivan' }, { 'nom': 'Lefebvre', 'prenom': 'Bob' }, { 'nom': 'Martin', 'prenom': 'George' }, { 'nom': 'Laurent', 'prenom': 'Fiona' }, { 'nom': 'Laurent', 'prenom': 'George' }, { 'nom': 'Durand', 'prenom': 'David' }, { 'nom': 'Simon', 'prenom': 'George' }, { 'nom': 'Leroy', 'prenom': 'Charlie' }, { 'nom': 'Lefebvre', 'prenom': 'Hannah' }, { 'nom': 'Martin', 'prenom': 'Fiona' }, { 'nom': 'Lefebvre', 'prenom': 'Charlie' }, { 'nom': 'Simon', 'prenom': 'Fiona' }, { 'nom': 'Petit', 'prenom': 'Ivan' }, { 'nom': 'Laurent', 'prenom': 'George' }, { 'nom': 'Michel', 'prenom': 'George' }, { 'nom': 'Michel', 'prenom': 'George' }, { 'nom': 'Leroy', 'prenom': 'Ivan' }, { 'nom': 'Lefebvre', 'prenom': 'Bob' }, { 'nom': 'Michel', 'prenom': 'Emma' }, { 'nom': 'Laurent', 'prenom': 'Alice' }, { 'nom': 'Martin', 'prenom': 'Bob' }, { 'nom': 'Moreau', 'prenom': 'Ivan' }, { 'nom': 'Dupont', 'prenom': 'Hannah' }, { 'nom': 'Durand', 'prenom': 'Fiona' }, { 'nom': 'Martin', 'prenom': 'Alice' }, { 'nom': 'Leroy', 'prenom': 'Hannah' }, { 'nom': 'Durand', 'prenom': 'Bob' }, { 'nom': 'Lefebvre', 'prenom': 'Emma' }, { 'nom': 'Dupont', 'prenom': 'Julia' }, { 'nom': 'Simon', 'prenom': 'George' }, { 'nom': 'Lefebvre', 'prenom': 'Charlie' }, { 'nom': 'Moreau', 'prenom': 'Alice' }, { 'nom': 'Petit', 'prenom': 'Hannah' }, { 'nom': 'Simon', 'prenom': 'Julia' }, { 'nom': 'Martin', 'prenom': 'Julia' }, { 'nom': 'Petit', 'prenom': 'Alice' }, { 'nom': 'Dupont', 'prenom': 'Bob' }, { 'nom': 'Michel', 'prenom': 'Alice' }, { 'nom': 'Dupont', 'prenom': 'Alice' }];
export default {
    name: 'AutocompleteSelectComponent',
    data() {
        return {
            search: '',
            filteredOptions: [],
        };
    },
    methods: {
        filterOptions() {
            if (!this.search) {
                this.filteredOptions = [];
            } else {
                this.filteredOptions = noms.filter(option =>
                    (option.prenom + ' ' + option.nom).toLowerCase().includes(this.search.toLowerCase())
                );
            }
        },
        selectOption(option) {
            this.search = option.prenom + ' ' + option.nom;
            this.filteredOptions = [];
        }
    }
};
</script>

<style scoped>
/* Ajoutez des styles ici */
.autocomplete-results {
    list-style-type: none;
    padding: 0;
}

.autocomplete-results li {
    cursor: pointer;
    padding: 8px;
    border-bottom: 1px solid #ddd;
}

.autocomplete-results li:hover {
    background-color: #f3f3f3;
}
</style>