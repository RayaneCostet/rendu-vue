<template>
  <div class="container w-4/5 mx-auto mt-4">
    <h1 class="text-lg font-bold">Ma sélection</h1>

    <div v-if="selection.length == 0">
      <p>Aucun cour sélectionné</p>
    </div>
    <div v-else>
      <div
        v-for="cour in selection"
        :key="cour.name" 
        class="border border-black my-4 p-2"
      >
        <h3>{{ cour.name }} ({{ cour.number }})</h3>
        <span>disponible le {{ cour.publicationdate }}</span>
        <img :src="require('../assets/img/' + player.photo)" alt="">
      </div>
    </div>

  </div>
  
</template>

<script>
export default {
  name: "selection-list",
  props: ['selection'],
}
</script>

<style>

</style>