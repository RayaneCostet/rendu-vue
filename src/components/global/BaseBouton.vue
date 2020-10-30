<template>
  <button class="bg-blue-500 text-white font-bold py-2 px-4 rounded">
    {{ text }}
  </button>
</template>

<script>
export default {
  props: ["text"],
};
</script>

<style scoped>
.btn-blue {
  @apply;
}
.btn-blue:hover {
  @apply bg-blue-700;
}
</style>
