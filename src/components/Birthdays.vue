<script setup lang="ts">
import { BirthdaysProps } from "../types/interfaces";
defineProps<{ birthdays: BirthdaysProps[]; deleteReminder: any }>();
</script>

<template>
  <div class="flex" v-for="birt in birthdays" :key="birt.id">
    <div class="flex m-5 items-center justify-around w-full">
      <img class="w-20 h-20 object-cover rounded-full" :src="birt.image" :alt="birt.name" />
      <div class="ml-4 text-left">
        <p class="font-bold text-xl tracking-wide">{{ birt.name }}</p>
        <p class="text-muted">{{ birt.age }} years</p>
      </div>
      <button @click="deleteReminder(birt.id, birt.name)">
        <i class="fa-solid fa-trash text-red-400"></i>
      </button>
    </div>
  </div>
</template>

<style></style>
