<template>
<div>
  <nav-bar
    @change-component="updateSelectedComponent"
  ></nav-bar>

  <keep-alive>
    <component 
      :is="selectedComponent"
      v-bind="currentProps"
      @update-selection="updateSelection"
    >
    </component>
  </keep-alive>
</div>
</template>

<script>
import CourList from './components/CourList.vue'
import SelectionList from './components/SelectionList.vue'
import NavBar from './components/navigation/NavBar.vue'
export default {
  name: 'App',
  components: {
    CourList,
    NavBar,
    SelectionList
  },
  data() {
    return {
      selectedComponent: 'cour-list',
      selectionArray: []
    }
  },
  computed: {
    currentProps() {
      if(this.selectedComponent == "selection-list") {
        return { selection: this.selectionArray }
      }
      return false
    }
  },
  methods: {
    updateSelectedComponent(comp) {
      this.selectedComponent = comp
    },
    updateSelection(cour) {
      this.selectionArray.push(cour)
    }
  }
}
</script>
<style>
</style>