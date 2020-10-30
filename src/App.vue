<template>
  <nav-bar
    @change-component="changeSelectedComponent"
  >
  </nav-bar>
  
  <keep-alive include="cour-list">
    <component 
      :is="selectedComponent"
      v-bind="currentProps"
      @child-event="selectionUpdate"
    >
    </component>
  </keep-alive>
  
</template>

<script>

import CourList from './components/CourList.vue'
import SelectionList from './components/SelectionList.vue'
import NavBar from './components/navigation/NavBar.vue'

export default {
  name: 'App',
  components: {
    CourList,
    SelectionList,
    NavBar
  },
  data() {
    return {
      selectedComponent: 'cour-list',
      courSelection: []
    }
  },
  computed: {
    currentProps() {
      if(this.selectedComponent == "selection-list"){
        return { selection: this.courSelection }
      }
      return false
    },
  },
  methods: {
    changeSelectedComponent(value) {
      this.selectedComponent = value
    },
    selectionUpdate(value) {
      this.courSelection.push(value)
    }
  }
}
</script>

<style>
 
</style>
