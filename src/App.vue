<script setup>

  const name = "Mariushkuta";
  const link = ref("https:/emanuel.ro");
  const number = ref(null);
  const counter = ref(0);
  const showCards = ref(false);

  import {ref, onMounted, onUpdated} from "vue";
  import Card from "./components/Card.vue";
  import StudentGrades from "./components/StudentGrades.vue";

  onMounted(() => {
    console.log("onMounted()");
  });

  onUpdated(() => {
    console.log("onUpdated()");
  });

  const clickHandler = () => {
    link.value = "https:/youtube.com";
  }

  const randomNumber = () => {
    number.value = Math.random().toFixed(2);
  }

  const increment = () => {
    counter.value++;
  }

</script>

<template>
  <h1>You did it {{name}}!</h1>
  <p>
    Visit <a href="https://vuejs.org/" target="_blank" rel="noopener">vuejs.org</a> to read the
    documentation
  </p>
  
  <button @click="clickHandler">Click me</button>
  <br><br>

  <a :href="link" target="_blank" rel="noopener noreferrer">Visit Emanuel website</a>
  <br>
  <input type="text" @change="console.log('input changed')"/>

  <br>
  <hr>
  <button @click="randomNumber">Generate random number</button>
  
  <div v-if="number">
    <h4>Random number is:</h4>

    <div v-if="number > 0.5">Number {{ number }} is bigger than 0.5</div>
    <div v-else>Number {{ number }} is smaller than 0.5</div>
  </div>
  <br>
  <hr>

  <button @click="increment">Click to increment: {{ counter }}</button>

<h3>Bootstrap-icon <i class="bi bi-airplane"></i></h3>
<StudentGrades />
<br><br>

<label for="cards">Show cards</label>
<input type="checkbox" id="cards" v-model="showCards">
<br><br>
<div v-if="showCards" class="card-wrapper">
  <Card id="1"/>
  <Card :id="3-1"/>
</div>

</template>

<style scoped>
/* @import "tailwindcss"; */
@import "bootstrap-icons";

.card-wrapper {
  display: flex;
  gap: 2rem;
}
</style>
