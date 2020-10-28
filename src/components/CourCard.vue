<template>
  
  <div 
    class="border border-green-900 m-2 p-2 rounded flex justify-between"
    :class="isInjuredClass"
  >
    <div>
      <h3 class="text-lg font-bold">{{ courName }} ({{ cour.number }})</h3>
      <p>{{ cour.position }}</p>
    </div>
    
    <base-button
      text="Sélectionner"
      @click="addToSelection"
    >
    </base-button>
  </div>
</template>

<script>
export default {
  name: "cour-card",
  props: ['cour'],
  computed: {
    courName() {
      if(this.cour.name.split('.').length > 1){
        return this.cour.name.split('.')[1]
      }
      return this.cour.name;
    },
    playerInjured() {
      if(this.cour.health == "out"){
        return true
      }
      return false
    },
    isInjuredClass() {
      return { 
        'bg-red-500': this.courInjured, 
        'bg-green-500': !this.courInjured 
        }
    },
  },
  methods: {
    addToSelection() {
      this.$emit('add-cour', this.cour)
    }
  }
}
</script>

<style scoped>
</style>