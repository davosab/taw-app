<script setup>
import {ref} from "vue";
const seeMore = () => alert("See more!");
const props = defineProps(["id"]);
const value = ref(props.id);
console.log(value);
</script>

<template>
<div class="card">
  <div class="image"></div>
  <h2>Card title {{ id }}</h2>
  <p>Card description.</p>
  <button @click="seeMore">See more</button>
</div>
</template>

<style scoped>
.image {
  height: 10em;
  background: rgb(21, 38, 78);
}
.card {
  border: 1px solid black;
  border-radius: 1rem;
  display: flex;
  flex-direction: column;
  padding: 1.5em 1em;
  width: 15em;
}
</style>