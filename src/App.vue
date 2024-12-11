<script setup lang="ts">
import { ref } from 'vue'
import Select from 'primevue/select';

const selectedCity = ref(null);
const categories = ref([
  { category: 'Grammaire' },
  { category: 'Orthographe' },
  { category: 'Accord' },
]);
</script>

<template>
  <div class="container mx-auto mt-4">
    <Select v-model="selectedCity" :options="categories" optionLabel="category" placeholder="Choisir une catégorie" class="w-full md:w-56" />
  </div>
</template>

<style scoped></style>
