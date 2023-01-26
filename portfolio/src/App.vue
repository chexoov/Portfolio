<template>
  <div
    id="screen"
    class="h-[100vh] bg-black grid grid-cols-[5fr_7fr] place-items-center"
  >
    <div id="hello">
      <Hello />
    </div>
    <div
      id="cards"
      class="bg-[#000] h-[100%] w-[100%] opacity-[0.01] transition ease-in-out scale-[90%]"
      :class="{ 'scale-[100%] opacity-[1] delay-[3s] duration-1000 ': isCardsMounted }"
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
.cards-load {
  animation: cards-appear 1s ease;
  animation-delay: 3s;
  /* opacity: 0; */
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
