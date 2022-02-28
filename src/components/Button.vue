<script setup lang="ts">
defineProps<{ reset: any }>();
</script>

<template>
  <button @click="reset()" class="w-full bg-red-300 font-bold tracking-wider text-white p-3 rounded-md transition-all hover:bg-red-400 mt-5">
    Clear All
  </button>
</template>

<style></style>
