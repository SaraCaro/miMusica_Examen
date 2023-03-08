<script setup>
import cabecera from './components/header.vue'
import discos from './components/discos.vue'


function buscar(palabra) {
  console.log(palabra)
}

</script>

<template>
  <header>
    <cabecera></cabecera>
  </header>

  <main>
      <discos @palabraFiltrada="buscar"></discos>
    
  </main>
</template>

<style scoped>

</style>
