<template>

  <img alt="Vue logo" src="../assets/img/logo.png">
  <div class="flex">
    <div class="w-1/5">
      <selection-box
        :selection="selection"
      >
      </selection-box>
    </div>
    

    <div class="w-4/5 mt-2">
      <cour-card 
        v-for="(cour, index) in team.cours"
        :key="index"
        :cour="cour"
        @add-cour="addCourToSelection"
        >
      </cour-card>
    </div>
    

  </div>
    
</template>

<script>
import CourCard from './CourCard.vue'
import SelectionBox from './SelectionBox.vue'

export default {
  name: "cour-view",
  components: {
    CourCard,
    SelectionBox
  },
  data() {
    return {
      selection: []
    }
  },
  methods: {
    addCourToSelection(cour){
      this.selection.push(cour)
      this.$emit('child-event', cour)
    }
  }
}
</script>

<style scoped>

</style>