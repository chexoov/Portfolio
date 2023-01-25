<template>
  <div id="screen" class="h-[100vh] bg-black grid grid-cols-[5fr_7fr] place-items-center">
    <div id="hello" class="hello-load">
      <Hello />
    </div>
    <div id="cards" class=" bg-[#000] h-[100%] w-[100%] cards-load">
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
  data() {
    return {
      isCardsMounted: false,
    }
  },
  mounted() {
    setTimeout(() => {
      this.isCardsMounted = !this.isCardsMounted;
    }, 4000);
  }
}

</script>


<style>
.hello-load {
  animation: hello-appear 5s ease;
}

@keyframes hello-appear {
  0% {
    opacity: 0;
  }
  20% {
    opacity: 1;
  }
  80% {
    opacity: 1;
  }
  100% {
    opacity: 1;
  }
}

.cards-load {
  animation: cards-appear 5s ease;
}
@keyframes cards-appear {
  0% {
    opacity: 0;
  }
  60% {
    opacity: 0;
  }
  80% {
    opacity: 1;
  }
  100% {
    opacity: 1;
  }
}

</style>
