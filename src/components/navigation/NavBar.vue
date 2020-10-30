<template>
  <div class="bg-blue-300 p-2" style="background-color: #38369A; color: #FFFF;">
    <a href="#" @click="changeComponent('cour-list')">Tous les cours</a> |
    <a href="#" @click="changeComponent('selection-list')">Ma sélection</a>
  </div>
</template>

<script>
export default {
  name: "nav-bar",
  methods: {
    changeComponent(value) {
      this.$emit("change-component", value);
    },
  },
};
</script>

<style></style>
