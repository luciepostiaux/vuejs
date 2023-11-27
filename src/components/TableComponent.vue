<!-- <template>
    <div>
        <table class="min-w-full">
            <thead>
                <tr>
                    <th v-for="column in columns" :key="column.key"
                        class="px-6 py-3 bg-gray-50 text-left text-xs leading-4 font-medium text-gray-500 uppercase tracking-wider">
                        {{ column.title }}
                    </th>
                </tr>
            </thead>
            <tbody class="bg-white">
                <tr v-for="(row, rowIndex) in rows" :key="rowIndex" class="hover:bg-gray-100">
                    <td v-for="column in columns" :key="column.key" class="px-6 py-4 whitespace-no-wrap">
                        {{ row[column.key] }}
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template> -->

<!-- <script setup>
import { defineProps } from 'vue';

const props = defineProps({
    rows: Array,
    columns: Array
});
</script>

<style>
/* Utilisez TailwindCSS pour le style */
</style> -->
