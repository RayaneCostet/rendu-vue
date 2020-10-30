<template>
  <button
    class="bg-green-500 hover:bg-gray-600 text-white font-bold py-2 px-4 rounded-full"
  >
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
