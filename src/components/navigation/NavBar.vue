<template>
  <div class="bg-blue-300 p-2">
    <a href="#" @click="changeComponent('cours-view')">Tous les cours</a> |
    <a href="#" @click="changeComponent('selection-list')"
      >Ma sélection de cours</a
    >
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
