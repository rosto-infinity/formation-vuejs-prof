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

const categories = ref([
  {
    id: 1,
    name: "Électronique",
    products: [
      { id: 101, name: "Téléphone" },
      { id: 102, name: "PC Portable" },
    ],
  },
  {
    id: 2,
    name: "Vêtements",
    products: [
      { id: 201, name: "T-Shirt" },
      { id: 202, name: "Jeans" },
    ],
  },
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


 <!-- --EXCELLENT : Un ID unique venant de la BDD comme clé -->
  <div v-for="user in users" :key="user.id">
    {{ user.name }} - {{ user.email }}
  </div>

  <!-- MAUVAIS ACTE : L'index comme clé (Cause de gros bugs lors des tris) -->
  <div v-for="(user, index) in users" :key="index">
    {{ user.name }}
  </div>

  <!-- #Le v-for sur une Plage de Nombres (Range) -->

  <!-- Affiche 1, 2, 3, 4, 5 -->
  <span v-for="n in 5" :key="n">{{ n }}</span>

  <!-- Pratique pour créer 10 fausses cartes (Skeleton Loaders) -->
  <div v-for="i in 10" :key="i" class="skeleton-item">
    Chargement élément {{ i }}...
  </div>

  <div v-for="category in categories" :key="category.id">
    <h3>{{ category.name }}</h3>
    <ul>
      <!-- Le v-for à l'intérieur utilise la variable `category` du v-for parent ! -->
      <li v-for="product in category.products" :key="product.id">
        {{ product.name }}
      </li>
    </ul>
  </div>
</template>
