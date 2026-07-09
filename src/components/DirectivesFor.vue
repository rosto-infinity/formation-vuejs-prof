<script setup>

import { ref, reactive } from "vue"
// #Rendu de Liste avec v-for (List Rendering)
const fruits = ref(["Pomme", "Banane", "Cerise", "Datte"]);

const tasks = ref([
  { id: 1, text: "Apprendre Vue", done: true },
  { id: 2, text: "Créer une appli", done: false },
  { id: 3, text: "Déployer en production", done: false },
]);

// L'Attribut key - Absolument Critique !

const users = ref([
  { id: 1, name: "Alice", email: "alice@exemple.com" },
  { id: 2, name: "Bob", email: "bob@exemple.com" },
  { id: 3, name: "Charlie", email: "charlie@exemple.com" },
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


 <!-- EXCELLENT : Un ID unique venant de la BDD comme clé -->
  <div v-for="user in users" :key="user.id">
    {{ user.name }} - {{ user.email }}
  </div>

  <!-- MAUVAIS ACTE : L'index comme clé (Cause de gros bugs lors des tris) -->
  <div v-for="(user, index) in users" :key="index">
    {{ user.name }}
  </div>
</template>
