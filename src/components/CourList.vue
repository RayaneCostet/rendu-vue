  
<template>
<div>
  <h1>Liste des cours {{ coursData.name }} </h1>

  <selection-box 
    :selection="selection"
  >
  </selection-box>

  <cour-card
    v-for="(cour, index) in coursData.cours"
    :key="index"
    :cour="cour"
    @add-cour="addCourToSelection"
    >
  </cour-card>
</div>
</template>

<script>
import coursData from '../assets/data/cours.json'
import CourCard from './CourCard.vue'
import SelectionBox from './SelectionBox.vue'
export default {
  name: "cour-List",
  components: {
    CourCard,
    SelectionBox
  },
  data() {
    return {
      coursData : coursData,
      selection: []
    }
  },
  methods: {
    addCourToSelection(cour) {
      this.selection.push(cour)
      this.$emit('update-selection', cour)
    }
  }
}
</script>

<style>
</style>