<script setup>
import {ref} from "vue";
const grades = ref([7, 8, 5, 10, 9]);
</script>

<template>
  <h3>Test v-for</h3>
  <ul>
    <li v-for="(grade, index) of grades" :key="index">
      Grade: {{ grade }}
    </li>
  </ul>
  <button @click="grades[0] = 10">Change first grade</button>
</template>

<style></style>