<template>
  <div
    id="screen"
    class="h-[100vh] bg-black grid md:grid-cols-[5fr_7fr] place-items-center max-md:grid-rows-[100vh_100vh]"
  >
    <div id="hello">
      <Hello />
    </div>
    <div
      id="cards"
      class="bg-[#000] h-[100%] w-[100%] transition ease-in-out cards-load"
      
    >
      <Cards />
    </div>
  </div>
</template>

<script lang="ts">
import { RouterLink, RouterView } from "vue-router";
import Hello from "./components/Hello.vue";
import Cards from "./components/Cards.vue";

export default {
  components: {
    Hello,
    Cards,
  },
  data() {
    return {
      isCardsMounted: false,
    };
  },
  mounted() {
    setTimeout(() => {
      this.isCardsMounted = true;
    }, 10);
  },
};
</script>

<style>
html {
  background-color: black;
}

body::-webkit-scrollbar {
  display: none;
}

/* Hide scrollbar for IE, Edge and Firefox */
body {
  -ms-overflow-style: none;  /* IE and Edge */
  scrollbar-width: none;  /* Firefox */
}


.cards-load {
  animation: cards-appear 1s ease forwards;
  animation-delay: 3s;
  opacity: 0.01;
}
@keyframes cards-appear {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

</style>
