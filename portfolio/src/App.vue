<template>
  <div id="screen" class="h-[100vh] bg-black grid grid-cols-[5fr_7fr] place-items-center">
    <div id="hello" class="">
      <Hello />
    </div>
    <div id="cards" class=" bg-[#000] h-[100%] w-[100%]">
      <Cards />
    </div>

  </div>
</template>


<script lang="ts">
import { RouterLink, RouterView } from "vue-router";
import Hello from './components/Hello.vue';
import Cards from './components/Cards.vue';

export default {
  components: {
    Hello,
    Cards
  },
}

</script>


<style>

/* CSS */

</style>
