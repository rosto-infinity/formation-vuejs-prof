<script setup>


import DirectivesCond from './components/DirectivesCond.vue';
import DirectivesFor from './components/DirectivesFor.vue';
import DirectivesVmodel from './components/DirectivesVmodel.vue';
// import Directives from './components/Directives.vue';
import MessageRendering from './components/MessageRendering.vue';


</script>

<template>
<!-- <MessageRendering /> -->
<!-- <Directives /> -->
<!-- <DirectivesCond/> -->
<!-- <DirectivesFor/> -->
<DirectivesVmodel/>
 
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
