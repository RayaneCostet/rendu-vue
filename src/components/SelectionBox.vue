<template>
  <div>
    Ma sélection : {{ selection.length }}
    <span v-if="nbrCours">cours</span>
    <span v-else>cour</span>
  </div>
</template>

<script>
export default {
  name: "selection-box",
  props: ["selection"],
  computed: {
    nbrCours() {
      if (this.selection.length > 1) {
        return true;
      }
      return false;
    },
  },
};
</script>

<style></style>
