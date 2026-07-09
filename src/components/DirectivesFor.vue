<script setup>

import { ref, reactive } from "vue"
// #Rendu de Liste avec v-for (List Rendering)
const fruits = ref(["Pomme", "Banane", "Cerise", "Datte"]);

const tasks = ref([
  { id: 1, text: "Apprendre Vue", done: true },
  { id: 2, text: "Créer une appli", done: false },
  { id: 3, text: "Déployer en production", done: false },
]);
</script>

<template>
 <div v-for=" fruit in fruits">
    {{ fruit }}

  </div>
  <ul>
 <!-- L'index commence à 0, comme en JS -->
 <li v-for="(task, index) in tasks" :key="task.id">
   {{ index + 1 }}. {{ task.text }}
   <span v-if="task.done"></span>
 </li>
</ul>
</template>
