<script setup>

import { ref } from "vue";
//1-----------------------------################
// const imageUrl = ref("/images/favicon.ico");
const linkUrl = ref("https://vuejs.org");
const inputId = ref("mon-email-input");

// const id = ref("mon-element");
const src = ref("/images/favicon.ico");
// const href = ref("https://exemple.com");
//2-----------------------------################
const isDisabled = ref(true);
const isRequired = ref(false);
const isChecked = ref(true);

</script>

<template>
<!-- //1-----------------------------################ -->
<!-- On lie (bind) l'attribut src -->
  <!-- <img :src="imageUrl" alt="Logo de l'app" /> -->
  <img :src alt="Logo de l'app" />

  <!-- On lie l'attribut href -->
  <a v-bind:href="linkUrl">Site Officiel de Vue.js</a>

  <!-- On lie l'attribut id -->
  <input v-bind:id="inputId" type="email" />
  <label v-bind:for="inputId">Votre Email :</label>


<!-- 2-----------------------------################ -->
 <!-- Puisque isDisabled est VRAI, le HTML final sera : <button disabled>...</button> -->
  <button :disabled="isDisabled">Vous ne pouvez pas cliquer ici</button>

  <!-- Puisque isRequired est FAUX, Vue supprime carrément l'attribut -->
  <!-- Résultat HTML : <input> (pas de required !) -->
  <input :required="isRequired" />

  <!-- Résultat : <input type="checkbox" checked> -->
  <input type="checkbox" :checked="isChecked" />
</template>
