<script setup>
import { computed, ref } from 'vue';

// État réactif (State)
const msg = ref('Mon apprentissage en vue js');
const count = ref(0);

//v-bind en css
 const color = ref('red')
 const fontSize =ref(16)

 // Propriétés calculées (Computed)
const doubleCount = computed(() => count.value * 2);

// Fonctions classiques
function increment(){
  count.value++;
}
// Propriétés calculées (Computed)

</script>

<template>
    <p class="text1"> Voir : {{ msg }} </p>
    <p>Compteur : {{ count }}</p>
    <p>Compteur : {{ doubleCount }}</p>
    <button @click="increment">Incrementer</button>
    

    <p class="text">Design totalement dynamique !</p>
    <button @click="color = 'blue'; fontSize = '23'">Passer au Bleu</button>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}
.text1{
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


  .text {
    /* Le CSS se mettra à jour en temps réel si la variable color change dans le JS ! */
    color: v-bind(color);
    font-size: v-bind(fontSize + 'px');
}
@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
