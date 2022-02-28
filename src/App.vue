<script setup lang="ts">
import { reactive } from "vue";
import data from "../data";
import Birthdays from "./components/Birthdays.vue";
import Button from "./components/Button.vue";

const state = reactive({
  birthdays: data,
});

const reset = () => {
  if (confirm("Are you sure ?")) {
    state.birthdays = [];
  }
};

const deleteReminder = (id: number, name: String) => {
  if (confirm(`Delete ${name} reminder?`)) {
    state.birthdays = state.birthdays.filter((reminder) => reminder.id !== id);
  }
};
</script>

<template>
  <div class="items-center justify-center container mx-auto w-96 rounded-md text-left bg-white mt-20 p-5 shadow-lg">
    <h1 class="font-normal text-2xl">{{ state.birthdays.length }} Birthdays today</h1>
    <Birthdays :birthdays="state.birthdays" :deleteReminder="deleteReminder" />
    <div v-if="state.birthdays.length > 0">
      <Button :reset="reset" />
    </div>
  </div>
</template>

<style scoped></style>
