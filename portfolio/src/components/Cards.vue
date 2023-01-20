<template>
  <div
    id="cardGroup"
    class="bg-black h-[100%] w-[100%] grid place-items-center"
  >
    <div
      @mouseover.capture="changeSquareHoverState()"
      @mouseleave.capture="changeSquareHoverState()"
      id="littleCardGit"
      class="transition squareTransitionFunc duration-[5s] z-[15] bg-[#ffffff2f] w-20 aspect-square rounded-xl absolute"
      :class="{
        'translate-x-[-8rem] translate-y-[-9rem] rotate-[8deg] hover:scale-110 duration-[1s] cursor-pointer delay-[2s]':
          isClicked,
        'delay-[0ms]': isOnPosition,
      }"
    >
      <a href="https://github.com/Inoooooor" target="_blank">
        <img
          src="../images/github.png"
          class="h-[100%] w-[100%]"
          alt="GitHub"
        />
      </a>
      <p
        class="text-white absolute transition translate-y-[-4rem] z-[-1]"
        :class="{' translate-x-[-4rem]': isGitSquareHovered}"
      >
        Мой GitHub
      </p>
    </div>
    <div
      id="littleCardTs"
      class="transition squareTransitionFunc duration-[5s] z-[35] bg-[#ffffff27] w-20 aspect-square rounded-xl absolute"
      :class="{
        'translate-x-[14rem] translate-y-[-7.5rem] rotate-[-2deg] hover:scale-110 duration-[1s]':
          isClicked,
        'delay-[0ms]': isOnPosition,
      }"
    ></div>
    <div
      id="littleCardVue"
      class="transition squareTransitionFunc duration-[5s] z-[15] bg-[#000000] w-20 aspect-square rounded-xl absolute"
      :class="{
        'translate-x-[-12rem] translate-y-[11rem] rotate-[-4deg] hover:scale-110 duration-[1s] delay-[4s]':
          isClicked,
        'delay-[0ms]': isOnPosition,
      }"
    ></div>
    <div
      id="littleCardTailwind"
      class="transition squareTransitionFunc duration-[5s] z-[15] w-20 aspect-square rounded-xl absolute"
      :class="{
        'translate-x-[-1rem] translate-y-[-14rem] rotate-[-4deg] hover:scale-110 duration-[1s] delay-[1.2s]':
          isClicked,
        'delay-[0ms]': isOnPosition,
      }"
    ></div>
    <div
      id="littleCardVite"
      class="transition squareTransitionFunc duration-[5s] z-[15] w-20 aspect-square rounded-xl absolute"
      :class="{
        'translate-x-[-14rem] translate-y-[15rem] rotate-[-14deg] hover:scale-110 duration-[1s] delay-[4.1s]':
          isClicked,
        'delay-[0ms]': isOnPosition,
      }"
    >
      <img src="../images/vite.png" alt="Vite" />
    </div>
    <div
      id="littleCardPinia"
      class="transition squareTransitionFunc duration-[5s] z-[15] w-20 aspect-square rounded-xl absolute"
      :class="{
        'translate-x-[-8rem] translate-y-[13rem] rotate-[14deg] hover:scale-110 duration-[1s] delay-[4.2s]':
          isClicked,
        'delay-[0ms]': isOnPosition,
      }"
    >
      <img src="../images/pinia.png" alt="Pinia" class="rounded-xl" />
    </div>
    <div
      id="littleCardfirebase"
      class="transition squareTransitionFunc duration-[5s] z-[15] w-20 aspect-square rounded-xl absolute"
      :class="{
        'translate-x-[-10rem] translate-y-[17rem] rotate-[14deg] hover:scale-110 duration-[1s] delay-[4.3s]':
          isClicked,
        'delay-[0ms]': isOnPosition,
      }"
    >
      <img src="../images/firebase.png" alt="firebase" class="rounded-xl" />
    </div>
    <div
      id="littleCardfigma"
      class="transition squareTransitionFunc duration-[5s] z-[15] w-20 aspect-square rounded-xl absolute"
      :class="{
        'translate-x-[-22rem] translate-y-[-3.5rem] rotate-[14deg] hover:scale-110 duration-[1s] delay-[3s]':
          isClicked,
        'delay-[0ms]': isOnPosition,
      }"
    >
      <img src="../images/figma.png" alt="figma" class="rounded-xl" />
    </div>
    <div
      id="littleCardphotoshop"
      class="transition squareTransitionFunc duration-[5s] z-[15] w-20 aspect-square rounded-xl absolute"
      :class="{
        'translate-x-[-22rem] translate-y-[1rem] rotate-[14deg] hover:scale-110 duration-[1s] delay-[3.1s]':
          isClicked,
        'delay-[0ms]': isOnPosition,
      }"
    >
      <img src="../images/photoshop.png" alt="photoshop" class="rounded-xl" />
    </div>
    <div
      id="littleCardillustrator"
      class="transition squareTransitionFunc duration-[5s] z-[15] w-20 aspect-square rounded-xl absolute"
      :class="{
        'translate-x-[-22rem] translate-y-[5.5rem] rotate-[14deg] hover:scale-110 duration-[1s] delay-[3.2s]':
          isClicked,
        'delay-[0ms]': isOnPosition,
      }"
    >
      <img
        src="../images/illustrator.png"
        alt="illustrator"
        class="rounded-xl"
      />
    </div>
    <div
      id="littleCardBootstrap"
      class="transition squareTransitionFunc duration-[5s] z-[15] w-20 aspect-square rounded-xl absolute"
      :class="{
        'translate-x-[4rem] translate-y-[-15rem] rotate-[14deg] hover:scale-110 duration-[1s] delay-[1s]':
          isClicked,
        'delay-[0ms]': isOnPosition,
      }"
    >
      <img src="../images/bootstrap.png" alt="Bootstrap" class="rounded-xl" />
    </div>
    <div
      id="littleCardsass"
      class="transition squareTransitionFunc duration-[5s] z-[15] w-20 aspect-square rounded-xl absolute"
      :class="{
        'translate-x-[-2rem] translate-y-[-17.5rem] rotate-[14deg] hover:scale-110 duration-[1s] delay-[1.1s]':
          isClicked,
        'delay-[0ms]': isOnPosition,
      }"
    >
      <img src="../images/sass.png" alt="sass" class="rounded-xl" />
    </div>
    <div
      id="littleCardHs"
      class="transition squareTransitionFunc duration-[5s] z-[15] bg-[#ffffff27] w-20 aspect-square rounded-xl absolute"
      :class="{
        'translate-x-[13rem] translate-y-[13.5rem] rotate-[12deg] hover:scale-110 duration-[1s] delay-[5s]':
          isClicked,
        'delay-[0ms]': isOnPosition,
      }"
    ></div>
    <div
      id="littleCardCheckers"
      @mouseover.capture="changeCheckerSquareState()"
      @mouseleave.capture="changeCheckerSquareState()"
      class="transition squareTransitionFunc duration-[5s] z-[15] bg-[#ffffff27] w-20 aspect-square rounded-xl absolute grid place-items-center"
      :class="{
        'translate-x-[7rem] translate-y-[15rem] rotate-[-12deg] hover:scale-110 duration-[1s] cursor-pointer delay-[5.1s]':
          isClicked,
        'delay-[0ms]': isOnPosition,
      }"
    >
      <p class=" leading-4 text-white transition text-center " :class="{ 'translate-x-[-5rem]': isCheckersSquareHovered }">Мои Онлайн Шашки (сырые)</p>
      </div>
    <div
      class="z-10 transition duration-500 bg-[#0055ff] w-48 aspect-[5/7] rounded-2xl absolute translate-x-1 rotate-1"
      :class="{
        'scale-105': isHovered,
        '-translate-x-[8rem] translate-y-[1rem] rotate-[-20deg]': isClicked,
      }"
      @click="changeClickState()"
      @mouseover="changeHoverState()"
      @mouseleave="changeHoverState()"
    ></div>
    <div
      class="z-20 transition duration-500 bg-[#00ff48] w-48 aspect-[5/7] rounded-2xl absolute translate-x-[-1rem] translate-y-2 rotate-[-4deg] shadow-[-20px_10px_20px_rgba(0,0,0,0.25)]"
      :class="{
        'scale-105': isHovered,
        'translate-x-[-2rem] translate-y-[0.5rem] rotate-[-7deg]': isClicked,
      }"
      @click="changeClickState()"
      @mouseover="changeHoverState()"
      @mouseleave="changeHoverState()"
    ></div>
    <div
      class="z-30 transition duration-500 bg-[#f9f942] w-48 aspect-[5/7] rounded-2xl absolute translate-x-[-0.5rem] translate-y-2 rotate-[-2deg] shadow-[-20px_10px_20px_rgba(0,0,0,0.25)]"
      :class="{
        'scale-105': isHovered,
        'translate-x-[4.1rem] translate-y-[0.5rem] rotate-[7deg]': isClicked,
      }"
      @click="changeClickState()"
      @mouseover="changeHoverState()"
      @mouseleave="changeHoverState()"
    ></div>
    <div
      class="z-40 transition duration-500 bg-[#ff003c] w-48 aspect-[5/7] rounded-2xl absolute translate-x-1 translate-y-2 rotate-6 shadow-[-20px_10px_20px_rgba(0,0,0,0.25)]"
      :class="{
        'scale-105': isHovered,
        'translate-x-[10rem] translate-y-[2rem] rotate-[20deg]': isClicked,
      }"
      @click="changeClickState()"
      @mouseover="changeHoverState()"
      @mouseleave="changeHoverState()"
    ></div>
    <!-- <div id="arrowPointer" class=" translate-x-[10rem] w-[5rem]">
      <img src="../images/arrow.gif" alt="">
    </div> -->
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      isHovered: false,
      isClicked: false,
      isOnPosition: false,
      isGitSquareHovered: false,
      isCheckersSquareHovered: false,
    };
  },
  methods: {
    changeHoverState() {
      this.isHovered = !this.isHovered;
    },
    changeSquareHoverState() {
      this.isGitSquareHovered = !this.isGitSquareHovered;
    },
    changePositionState() {
      this.isOnPosition = !this.isOnPosition;
    },
    changeCheckerSquareState() {
      this.isCheckersSquareHovered = !this.isCheckersSquareHovered;
    },
    changeClickState() {
      if (this.isOnPosition) {
        this.changePositionState();
      } else {
        setTimeout(this.changePositionState, 5200);
      }
      this.isClicked = !this.isClicked;
    },
  },
};
</script>

<style scoped>
/* #cardGroup:hover > #bigCard:nth-child(1) {
  transform: translateX(-50px);
} */

.squareTransitionFunc {
  transition-timing-function: cubic-bezier(0.11, 0.86, 0, 1.06);
}

#littleCardGit {
  /* background-image: url('../images/github.png'); */
  background-size: contain;
}

#littleCardTs {
  background-image: url("../images/ts.png");
  background-size: contain;
}

#littleCardVue {
  background-image: url("../images/vue.png");
  background-size: contain;
}

#littleCardHs {
  background-image: url("../images/hs.png");
  background-size: contain;
}

#littleCardCheckers {
  background-image: url("../images/checkers.png");
  background-size: contain;
}

#littleCardTailwind {
  background-image: url("../images/tailwind.png");
  background-size: contain;
}
</style>
