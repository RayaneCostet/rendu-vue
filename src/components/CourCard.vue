<template>
  <div
    class="border border-green-900 m-2 p-2  flex justify-between"
    :class="isUnavailableClass"
  >
    <div>
      <h3 class="text-lg font-bold">{{ courName }}</h3>
      <p>{{ cour.available }} {{ cour.unavailable }}</p>
    </div>

    <base-button text="Sélectionner" @click="addToSelection"> </base-button>
  </div>
</template>

<script>
export default {
  name: "cour-card",
  props: ["cour"],
  computed: {
    courName() {
      if (this.cour.name.split(".").length > 1) {
        return this.cour.name.split(".")[1];
      }
      return this.cour.name;
    },
    courUnavailable() {
      if (this.cour.unavailable == "en cours") {
        return true;
      }
      return false;
    },
    isUnavailableClass() {
      return {
        "bg-red-700": this.courUnavailable,
        "border-white": this.courUnavailable,
        "border-black": !this.courUnavailable,
      };
    },
  },
  methods: {
    addToSelection() {
      this.$emit("add-cour", this.cour);
    },
  },
};
</script>

<style scoped></style>
