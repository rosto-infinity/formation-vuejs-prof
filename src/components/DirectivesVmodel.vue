<script setup>

import { ref, reactive } from "vue"
// Déclaration de la variable réactive
const message = ref("")
</script>

<template>
 
  <input v-model="message" placeholder="edit me" />
  <p>Message is: {{ message }}</p>
</template>
