<script setup>

import { ref, reactive } from "vue"

// Rendu Conditionnel avec v-if et v-show (Conditional Rendering)
// La Directive v-if
  const isLoggedIn = ref(true);
const hasPermission = ref(true);
</script>

<template>
  <div v-if="isLoggedIn">
    <p>Heureux de vous revoir !</p>
    <button>Se déconnecter</button>
  </div>

  <div v-if="hasPermission">
    <p>Vous avez le droit de voir ce contenu.</p>
  </div>
</template>
