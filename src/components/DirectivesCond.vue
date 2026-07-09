<script setup>

import { ref, reactive } from "vue"

// Rendu Conditionnel avec v-if et v-show (Conditional Rendering)
// La Directive v-if
  const isLoggedIn = ref(true);
const hasPermission = ref(true);


// #La Directive v-show
const isVisible = ref(true);
</script>

<template>
  <div v-if="isLoggedIn">
    <p>Heureux de vous revoir !</p>
    <button>Se déconnecter</button>
  </div>

  <div v-if="hasPermission">
    <p>Vous avez le droit de voir ce contenu.</p>
  </div>

  <div v-show="isVisible">
    J'existe TOUJOURS dans le DOM (la page web), je suis juste masqué avec
    'display: none' si beoin.
  </div>

  <button @click=" ()=>{isVisible = !isVisible}">Basculer la Visibilité</button>


  <!-- Si vous utilisez <template>, vous DEVEZ utiliser v-if. Si vous voulez vraiment un v-show, vous devez créer un vrai <div>. -->

<!-- #Le Pire Crime : v-if sur la même ligne qu'un v-for -->
<!-- Ne mettez JAMAIS un v-if et un v-for sur le même élément ! C'est formellement interdit par l'ESLint officiel de Vue. Le v-if a la priorité la plus forte et tentera de s'exécuter AVANT la boucle de la ligne, ce qui finira immanquablement par un beau crash. -->

 <li v-for="user in users" v-if="user.isActive">...</li>

<!-- --BIEN : On enveloppe d'abord, on filtre ensuite -->
<template v-for="user in users" :key="user.id">
  <li v-if="user.isActive">{{ user.name }}</li>
</template>

<!-- EXCELLENT (La Méthode Royale) : On filtre via une Propriété Calculée (Computed JS) -->
<li v-for="user in activeUsers" :key="user.id">{{ user.name }}</li>
</template>
