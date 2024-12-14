<script setup lang="ts">
import { ref } from 'vue'
import RowComponent from './components/RowComponent.vue'
import Button from 'primevue/button'

const rows = ref([{}]) // Start with one row

const handleAddClick = () => {
  rows.value.push({}) // Add a new item to the list
}

const handleRowRemove = (index: number) => {
  if (rows.value.length === 1) {
    return // Do not remove the last row
  }
  rows.value.splice(index, 1)
}

const handlePrint = () => {
  window.print()
}
</script>

<template>
  <div class="container mx-auto mt-4 print:mx-0 print:mt-0">
    <h1 class="text-2xl font-bold py-2">Méthode de correction</h1>
    <div id="rowList">
      <RowComponent v-for="(row, index) in rows" :key="index" @remove="handleRowRemove(index)" />
    </div>
    <div class="float-right space-x-4 print:hidden">
      <Button
        type="button"
        label="Imprimer"
        icon="pi pi-print"
        @click="handlePrint"
        severity="info"
      />
      <Button rounded icon="pi pi-plus" aria-label="Add" @click="handleAddClick" />
    </div>
  </div>
</template>
