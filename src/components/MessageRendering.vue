<script setup>
import {ref} from 'vue';

const msg = ref('Mon apprentissage en vue js');

const count = ref(0);
function increment(){
  count.value++;
}
</script>

<template>
    <p class="text"> Voir : {{ msg }} </p>
    <p>Compteur : {{ count }}</p>
    <button @click="increment">Incrementer</button>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}
.text{
  color:rgb(3, 199, 3);
  font-size: 2rem;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
