<script setup>

import { ref, reactive } from "vue";
//1-----------------------------################
// -const imageUrl = ref("/images/favicon.ico");
const linkUrl = ref("https://vuejs.org");
const inputId = ref("mon-email-input");

// -const id = ref("mon-element");
const src = ref("/images/favicon.ico");
// const href = ref("https://exemple.com");
//2-----------------------------################
const isDisabled = ref(true);
const isRequired = ref(false);
const isChecked = ref(true);

// Lier de Multiples Attributs d'un seul coup
const inputAttrs = reactive({
  id: "email-field",
  type: "email",
  placeholder: "Entrez votre adresse email",
  required: true,
});

const imageAttrs = ref({
  src: "/images/avatar.jpg",
  alt: "Avatar Utilisateur",
  width: 100,
  height: 100,
});


const attributeName = ref("title"); // L'attribut ciblé est "title"
const attributeValue = ref("Ceci est une infobulle !");


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
  <input type="checkbox" :checked="isChecked" /><br><br>

   <!-- Déballe ("splat") absolument tous les attributs de l'objet d'un coup ! -->
  <input v-bind="inputAttrs" />
  <!-- Rendu HTML : <input id="email-field" type="email" placeholder="..." required> -->

  <img v-bind="imageAttrs" />
  <!-- Rendu HTML : <img src="/images/avatar.jpg" alt="..." width="100" height="100"> -->

 <!-- Vue va générer :votre_nom_d_attribut="Valeur" -->
  <div :[attributeName]="attributeValue">Survolez-moi avec la souris !</div>
  <!-- Résultat : <div title="Ceci est une infobulle !">...</div> -->
</template>
