<template>
    <div
      id="cardGroup"
      class="bg-black bg-opacity-0 h-[100%] w-[100%] grid place-items-center transition duration-1000 select-none relative max-md:scale-50"
      
    >
      <div
        @mouseover.capture="changeSquareHoverState()"
        @mouseleave.capture="changeSquareHoverState()"
        id="littleCardGit"
        class="transition squareTransitionFunc duration-[5s] z-[15] bg-[#ffffff2f] w-20 aspect-square rounded-xl absolute"
        :class="{
          'translate-x-[-8rem] translate-y-[-9rem] rotate-[8deg] hover:scale-110 duration-[1s] cursor-pointer ':
            isClicked,
          'delay-[0ms]': isOnPosition,
          'delay-[2s]': !isOnPosition && isClicked,
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
          :class="{ ' translate-x-[-4rem]': isGitSquareHovered }"
        >
          Мой GitHub
        </p>
      </div>
      <div
        id="littleCardBot"
        class="transition squareTransitionFunc duration-[5s] z-[15]  w-20 aspect-square rounded-xl absolute"
        :class="{
          'translate-x-[-12rem] translate-y-[-15rem] rotate-[8deg] hover:scale-110 duration-[1s] cursor-pointer ':
            isClicked,
          'delay-[0ms]': isOnPosition,
          'delay-[1.8s]': !isOnPosition && isClicked,
        }"
      >
          <img
          @mouseover.capture="changeBotHoverState()"
          @mouseleave.capture="changeBotHoverState()"
            src="../images/bot.png"
            class="h-[100%] w-[100%]"
            alt="GitHub"
          />
        <p
          class="text-white absolute transition translate-y-[-4rem] z-[-1] text-sm pl-2"
          :class="{ ' translate-x-[-4rem]': isBotSquareHovered }"
        >
          Телеграм боты
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
          'translate-x-[-12rem] translate-y-[11rem] rotate-[-4deg] hover:scale-110 duration-[1s] ':
            isClicked,
          'delay-[0ms]': isOnPosition,
          'delay-[4s]': !isOnPosition && isClicked,
        }"
      ></div>
      <div
        id="littleCardTailwind"
        class="transition squareTransitionFunc duration-[5s] z-[15] w-20 aspect-square rounded-xl absolute"
        :class="{
          'translate-x-[-1rem] translate-y-[-14rem] rotate-[-4deg] hover:scale-110 duration-[1s] ':
            isClicked,
          'delay-[0ms]': isOnPosition,
          'delay-[1.2s]': !isOnPosition && isClicked,
        }"
      ></div>
      <div
        id="littleCardVite"
        class="transition squareTransitionFunc duration-[5s] z-[15] w-20 aspect-square rounded-xl absolute"
        :class="{
          'translate-x-[-14rem] translate-y-[15rem] rotate-[-14deg] hover:scale-110 duration-[1s] ':
            isClicked,
          'delay-[0ms]': isOnPosition,
          'delay-[4.1s]': !isOnPosition && isClicked,
        }"
      >
        <img src="../images/vite.png" alt="Vite" />
      </div>
      <div
        id="littleCardPinia"
        class="transition squareTransitionFunc duration-[5s] z-[15] w-20 aspect-square rounded-xl absolute"
        :class="{
          'translate-x-[-8rem] translate-y-[13rem] rotate-[14deg] hover:scale-110 duration-[1s] ':
            isClicked,
          'delay-[0ms]': isOnPosition,
          'delay-[4.2s]': !isOnPosition && isClicked,
        }"
      >
        <img src="../images/pinia.png" alt="Pinia" class="rounded-xl" />
      </div>
      <div
        id="littleCardfirebase"
        class="transition squareTransitionFunc duration-[5s] z-[15] w-20 aspect-square rounded-xl absolute"
        :class="{
          'translate-x-[-10rem] translate-y-[17rem] rotate-[14deg] hover:scale-110 duration-[1s] ':
            isClicked,
          'delay-[0ms]': isOnPosition,
          'delay-[4.3s]': !isOnPosition && isClicked,
        }"
      >
        <img src="../images/firebase.png" alt="firebase" class="rounded-xl" />
      </div>
      <div
        id="littleCardfigma"
        class="transition squareTransitionFunc duration-[5s] z-[15] w-20 aspect-square rounded-xl absolute"
        :class="{
          'translate-x-[-22rem] translate-y-[-3.5rem] rotate-[14deg] hover:scale-110 duration-[1s] ':
            isClicked,
          'delay-[0ms]': isOnPosition,
          'delay-[3s]': !isOnPosition && isClicked,
        }"
      >
        <img src="../images/figma@0.25x.png" alt="figma" class="rounded-xl" />
      </div>
      <div
        id="littleCardphotoshop"
        class="transition squareTransitionFunc duration-[5s] z-[15] w-20 aspect-square rounded-xl absolute"
        :class="{
          'translate-x-[-22rem] translate-y-[1rem] rotate-[14deg] hover:scale-110 duration-[1s] ':
            isClicked,
          'delay-[0ms]': isOnPosition,
          'delay-[3.1s]': !isOnPosition && isClicked,
        }"
      >
        <img src="../images/photoshop.png" alt="photoshop" class="rounded-xl" />
      </div>
      <div
        id="littleCardillustrator"
        class="transition squareTransitionFunc duration-[5s] z-[15] w-20 aspect-square rounded-xl absolute"
        :class="{
          'translate-x-[-22rem] translate-y-[5.5rem] rotate-[14deg] hover:scale-110 duration-[1s] ':
            isClicked,
          'delay-[0ms]': isOnPosition,
          'delay-[3.2s]': !isOnPosition && isClicked,
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
          'translate-x-[4rem] translate-y-[-15rem] rotate-[14deg] hover:scale-110 duration-[1s] ':
            isClicked,
          'delay-[0ms]': isOnPosition,
          'delay-[1s]': !isOnPosition && isClicked,
        }"
      >
        <img src="../images/bootstrap.png" alt="Bootstrap" class="rounded-xl" />
      </div>
      <div
        id="littleCardsass"
        class="transition squareTransitionFunc duration-[5s] z-[15] w-20 aspect-square rounded-xl absolute"
        :class="{
          'translate-x-[-2rem] translate-y-[-17.5rem] rotate-[14deg] hover:scale-110 duration-[1s] ':
            isClicked,
          'delay-[0ms]': isOnPosition,
          'delay-[1.1s]': !isOnPosition && isClicked,
        }"
      >
        <img src="../images/sass.png" alt="sass" class="rounded-xl" />
      </div>
      <div
        id="littleCardHs"
        class="transition squareTransitionFunc duration-[5s] z-[15] bg-[#ffffff27] w-20 aspect-square rounded-xl absolute"
        :class="{
          'translate-x-[13rem] translate-y-[13.5rem] rotate-[12deg] hover:scale-110 duration-[1s] ':
            isClicked,
          'delay-[0ms]': isOnPosition,
          'delay-[5s]': !isOnPosition && isClicked,
        }"
      ></div>
      <div
        id="littleCardCheckers"
        class="transition squareTransitionFunc duration-[5s] z-[15] bg-[#ffffff27] w-20 aspect-square rounded-xl absolute grid place-items-center"
        :class="{
          'translate-x-[7rem] translate-y-[15rem] rotate-[-12deg] hover:scale-110 duration-[1s] cursor-pointer ':
            isClicked,
          'delay-[0ms]': isOnPosition,
          'delay-[5.1s]': !isOnPosition && isClicked,
        }"
      >
        <a href="https://checkers-1bbc2.web.app/" target="_blank">
          <img
            @mouseover.capture="changeCheckerSquareState()"
            @mouseleave.capture="changeCheckerSquareState()"
            src="../images/checkers.png"
            alt="Checkers"
            class="h-[100%] w-[100%] rounded-2xl"
          />
        </a>
        <p
          class="leading-4 text-white transition text-center absolute -z-[1]"
          :class="{ 'translate-x-[-5rem]': isCheckersSquareHovered }"
        >
          Мои Онлайн Шашки (сырые)
        </p>
      </div>
      <div
        class="z-10 transition duration-500 bg-white w-48 aspect-[5/7] rounded-2xl absolute translate-x-1 rotate-1"
        :class="{
          'scale-105': isHovered,
          '-translate-x-[8rem] translate-y-[1rem] rotate-[-20deg]': isClicked,
        }"
        @click="changeClickState()"
        @mouseover="changeHoverState()"
        @mouseleave="changeHoverState()"
      >
      <img src="../images/spa.png" alt="spa" class=" rounded-[inherit] border-2 border-white">
    </div>
    <div
    class="example1 z-20 transition duration-500 bg-black w-48 aspect-[5/7] rounded-2xl absolute translate-x-[-1rem] translate-y-2 rotate-[-4deg] shadow-[-20px_10px_20px_rgba(0,0,0,0.25)] border-[3px] border-white"
    :class="{
      'scale-105': isHovered,
      'translate-x-[-2rem] translate-y-[0.5rem] rotate-[-7deg]': isClicked,
    }"
        @click="changeClickState()"
        @mouseover="changeHoverState()"
        @mouseleave="changeHoverState()"
        >
        <!-- <img src="../images/games.png" alt="gif" class="rounded-2xl"> -->
        <p>HTML ㅤㅤㅤCSS </p>
        <p>SPA ㅤㅤㅤREST</p>
        <p>AXIOS ㅤㅤㅤJSON</p>
        <p>NPM ㅤㅤㅤBEM</p>

      </div>
      <div
      class=" z-30 transition duration-500 bg-white w-48 aspect-[5/7] rounded-2xl absolute translate-x-[-0.5rem] translate-y-2 rotate-[-2deg] shadow-[-20px_10px_20px_rgba(0,0,0,0.25)]"
      :class="{
        'scale-105': isHovered,
        'translate-x-[4.1rem] translate-y-[0.5rem] rotate-[7deg]': isClicked,
      }"
        @click="changeClickState()"
        @mouseover="changeHoverState()"
        @mouseleave="changeHoverState()"
        >
        <img src="../images/games.png" alt="gif" class="rounded-2xl border-2 border-white">
        <!-- <p>HTML ㅤㅤㅤCSS </p>
        <p>SPA ㅤㅤㅤREST</p>
        <p>AXIOS ㅤㅤㅤJSON</p>
        <p>NPM ㅤㅤㅤBEM</p> -->
        
      </div>
      <div
      class="border-2 border-white z-40 transition duration-500 w-48 aspect-[5/7] rounded-2xl absolute translate-x-1 translate-y-2 rotate-6 shadow-[-20px_10px_20px_rgba(0,0,0,0.25)] bg-white"
      :class="{
        'scale-105': isHovered,
        'translate-x-[10rem] translate-y-[2rem] rotate-[20deg]': isClicked,
      }"
        @click="changeClickState()"
        @mouseover="changeHoverState()"
        @mouseleave="changeHoverState()"
        >
        <!-- <img src="../images/My_face.jpg" alt="gif" class="h-[100%] rounded-2xl border-2 border-white"> -->
        <img src="../images/My_face.jpg" alt="gif" class="h-[100%] rounded-2xl">
        <!-- <p>HTMLㅤㅤㅤCSS </p>
        <p>SPAㅤㅤㅤREST</p>
        <p>AXIOSㅤㅤㅤJSON</p>
        <p>NPMㅤㅤㅤBEM</p> -->
      </div>
      <!-- <div id="arrowPointer" class=" translate-x-[10rem] w-[5rem]">
        <img src="../images/arrow.gif" alt="">
      </div> -->
    </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      isMounted: false,
      isHovered: false,
      isClicked: false,
      isOnPosition: false,
      isGitSquareHovered: false,
      isCheckersSquareHovered: false,
      isBotSquareHovered: false,
    };
  },
  computed: {
    mountedGetter() {
      return this.isMounted ? true : false;
    },
  },
  methods: {
    changeHoverState() {
      this.isHovered = !this.isHovered;
    },
    changeSquareHoverState() {
      this.isGitSquareHovered = !this.isGitSquareHovered;
    },
    changeBotHoverState() {
      this.isBotSquareHovered = !this.isBotSquareHovered;
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
        setTimeout(() => {
          this.changePositionState();
          return;
        }, 5200);
      }
      this.isClicked = !this.isClicked;
      console.log('now it\'s', this.isClicked)
    },
  },
  mounted() {
    setTimeout(() => {
      this.isMounted = !this.isMounted;
    }, 1000)
  }
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
  background-image: url("../images/hs@0.1x.png");
  background-size: contain;
}

#littleCardCheckers {
  /* background-image: url("../images/checkers.png"); */
  background-size: contain;
}

#littleCardTailwind {
  background-image: url("../images/tailwind.png");
  background-size: contain;
}

.example1 {
 overflow: hidden;
 position: relative;
}
.example1 p {
 font-size: 6rem;
 color: rgb(52, 52, 52);
 position: absolute;
 width: 200%;
 /* height: 100%; */
 margin: 0;
 /* line-height: 50px; */
 text-align: center;
 /* Starting position */
 -moz-transform:translateX(100%);
 -webkit-transform:translateX(100%);	
 transform:translateX(100%);
 /* Apply animation to this element */	
 -moz-animation: example1 20s linear infinite;
 -webkit-animation: example1 20s linear infinite;
 animation: example1 20s linear infinite;
 /* background-color: rgb(61, 61, 61); */
}

.example1 p:nth-child(2){
 font-size: 2em;
 color: rgb(213, 213, 213);
 position: absolute;
 width: 130%;
 top: 34%;
 /* height: 100%; */
 margin: 0;
 line-height: 50px;
 text-align: center;
 /* Starting position */
 -moz-transform:translateX(100%);
 -webkit-transform:translateX(100%);	
 transform:translateX(100%);
 /* Apply animation to this element */	
 -moz-animation: example1 10s linear infinite;
 -webkit-animation: example1 10s linear infinite;
 animation: example1 10s linear infinite;
 /* background-color: rgb(61, 61, 61); */
}
.example1 p:nth-child(3){
 font-size: 3em;
 color: rgb(122, 122, 122);
 position: absolute;
 width: 150%;
 top: 50%;
 /* height: 100%; */
 margin: 0;
 line-height: 50px;
 text-align: center;
 /* Starting position */
 -moz-transform:translateX(100%);
 -webkit-transform:translateX(100%);	
 transform:translateX(100%);
 /* Apply animation to this element */	
 -moz-animation: example1 15s linear infinite;
 -webkit-animation: example1 15s linear infinite;
 animation: example1 15s linear infinite;
 /* background-color: rgb(61, 61, 61); */
}
.example1 p:nth-child(4){
 font-size: 3em;
 color: rgb(122, 122, 122);
 position: absolute;
 width: 180%;
 top: 3%;
 /* height: 100%; */
 margin: 0;
 line-height: 50px;
 text-align: center;
 /* Starting position */
 -moz-transform:translateX(100%);
 -webkit-transform:translateX(100%);	
 transform:translateX(100%);
 /* Apply animation to this element */	
 -moz-animation: example1 15s linear infinite;
 -webkit-animation: example1 15s linear infinite;
 animation: example1 15s linear infinite;
 /* background-color: rgb(61, 61, 61); */
}
/* Move it (define the animation) */
@-moz-keyframes example1 {
 0%   { -moz-transform: translateX(100%); }
 100% { -moz-transform: translateX(-100%); }
}
@-webkit-keyframes example1 {
 0%   { -webkit-transform: translateX(100%); }
 100% { -webkit-transform: translateX(-100%); }
}
@keyframes example1 {
 0%   { 
 -moz-transform: translateX(100%); /* Firefox bug fix */
 -webkit-transform: translateX(100%); /* Firefox bug fix */
 transform: translateX(100%); 		
 }
 100% { 
 -moz-transform: translateX(-100%); /* Firefox bug fix */
 -webkit-transform: translateX(-100%); /* Firefox bug fix */
 transform: translateX(-100%); 
 }
}
.example1:before, .example1:after {
  position: absolute;
  top: 0;
  width: 3rem;
  height: 100%;
  content: "";
  z-index: 1;
}
.example1:before {
  left: 0;
  background: linear-gradient(to right, #111 0%, transparent 100%);
}
.example1:after {
  right: 0;
  background: linear-gradient(to left, #111 0%, transparent 100%);
}
</style>
