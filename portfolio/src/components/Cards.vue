<template>
  <div
  id="cardGroup"
  class="bg-black bg-opacity-0 h-[100%] w-[100%] grid place-items-center transition duration-1000 select-none relative max-md:scale-50"
  >
  <div><input v-model.trim="newObj.key"/></div>
  
    <SmallCard
      v-for="(card, index) in cardsData"
      v-bind="{ ...card, isClicked }"
      :key="index"
    />

    <BigCard
      @click="changeClickState()"
      v-for="(card, index) in BigCardData"
      v-bind="{ ...card, isClicked, isHovered }"
      :key="index"
    >
      <p v-if="!card.img">HTML ㅤㅤㅤCSS</p>
      <p v-if="!card.img">SPA ㅤㅤㅤREST</p>
      <p v-if="!card.img">AXIOS ㅤㅤㅤJSON</p>
      <p v-if="!card.img">NPM ㅤㅤㅤBEM</p>
    </BigCard>
  </div>
</template>

<script lang="ts">
import SmallCard from "./SmallCard.vue";
import BigCard from "./BigCard.vue";

export default {
  components: { SmallCard, BigCard },


  data() {
    return {
      newObj: { key: "value" },
      isMounted: false,
      isHovered: false,
      isClicked: false,
      isOnPosition: false,
      isGitSquareHovered: false,
      isCheckersSquareHovered: false,
      isBotSquareHovered: false,
      cardsData: [
        {
          delay: 2,
          x: -10,
          y: -10.5,
          img: "src/images/github.png",
          rotate: 8,
          z: "15",
          link: "https://github.com/Inoooooor",
          duration: 1,
          label: "мой GitHub",
        },
        {
          delay: 1.8,
          x: -17,
          y: -16.5,
          img: "src/images/bot.png",
          rotate: 6,
          z: "15",
          link: "#",
          duration: 1,
          label: "<p>мой</p> <p>бот</p>",
        },
        {
          delay: 0,
          x: 16,
          y: -7.5,
          img: "src/images/ts.png",
          rotate: -4,
          z: "35",
          link: "#",
          duration: 1,
        },
        {
          delay: 2,
          x: -15,
          y: 8,
          img: "src/images/vue.png",
          rotate: -2,
          z: "15",
          link: "#",
          duration: 1,
        },
        {
          delay: 1.2,
          x: 5.5,
          y: -14,
          img: "src/images/tailwind.png",
          rotate: -12,
          z: "15",
          link: "#",
          duration: 1,
        },
        {
          delay: 4.1,
          x: -18.5,
          y: 11,
          img: "src/images/vite.png",
          rotate: -11,
          z: "15",
          link: "#",
          duration: 1,
        },
        {
          delay: 4.2,
          x: -7,
          y: 13,
          img: "src/images/pinia.png",
          rotate: 15,
          z: "15",
          link: "#",
          duration: 1,
        },
        {
          delay: 4.3,
          x: -8,
          y: 18,
          img: "src/images/firebase.png",
          rotate: 12,
          z: "15",
          link: "#",
          duration: 1,
        },
        {
          delay: 3,
          x: -24,
          y: -2.5,
          img: "src/images/figma@0.25x.png",
          rotate: 10,
          z: "15",
          link: "#",
          duration: 1,
        },
        {
          delay: 3.1,
          x: -27,
          y: 3,
          img: "src/images/photoshop.png",
          rotate: 10,
          z: "15",
          link: "#",
          duration: 1,
        },
        {
          delay: 3.2,
          x: -21.5,
          y: 5.5,
          img: "src/images/illustrator.png",
          rotate: 9,
          z: "15",
          link: "#",
          duration: 1,
        },
        {
          delay: 1,
          x: 2,
          y: -20,
          img: "src/images/bootstrap.png",
          rotate: 14,
          z: "15",
          link: "#",
          duration: 1,
        },
        {
          delay: 1.1,
          x: -6,
          y: -18.5,
          img: "src/images/sass.png",
          rotate: 14,
          z: "15",
          link: "#",
          duration: 1,
        },
        {
          delay: 5,
          x: 15,
          y: 7.5,
          img: "src/images/hs.png",
          rotate: 12,
          z: "15",
          link: "#",
          duration: 1,
        },
        {
          delay: 5.1,
          x: 4,
          y: 12,
          img: "src/images/checkers.png",
          rotate: -5,
          z: "15",
          link: "#",
          duration: 1,
          label: " Мои Онлайн Шашки (сырые)",
        },
      ],
      BigCardData: [
        {
          xInitial: 1,
          yInitial: -0.5,
          rotateInitial: 0.5,
          x: -9,
          y: -1.5,
          img: "src/images/spa.png",
          rotate: -20,
          z: "10",
          link: "#",
          duration: 0.5,
          label: "",
        },
        {
          xInitial: 0,
          yInitial: 0,
          rotateInitial: -6,
          x: 4,
          y: 0,
          img: "src/images/games.png",
          rotate: 4,
          z: "30",
          link: "#",
          duration: 0.5,
          label: "",
        },
        {
          xInitial: 1,
          yInitial: 0,
          rotateInitial: 3,
          x: 9.5,
          y: 0,
          img: "src/images/newFace.jpeg",
          rotate: 12,
          z: "40",
          link: "#",
          duration: 0.5,
          label: "",
        },
        {
          xInitial: -2,
          yInitial: 0.5,
          rotateInitial: -17,
          x: -2,
          y: 0.5,
          img: "",
          rotate: -7,
          z: "20",
          link: "#",
          duration: 0.5,
          label: "",
        },
      ],
    };
  },
  computed: {
    mountedGetter() {
      return this.isMounted ? true : false;
    },
  },
  mounted() {
    console.log(this.newObj.key);
    this.newObj.key = "key";
  },
  watch: {
    'newObj.key'(newValue, oldValue) {
      console.log(newValue, oldValue)
    }
  },
  methods: {
    changeHoverState() {
      console.log("change");
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
      console.log("now it's", this.isClicked);
    },
  },
  mounted() {
    setTimeout(() => {
      this.isMounted = !this.isMounted;
    }, 1000);
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
  -moz-transform: translateX(100%);
  -webkit-transform: translateX(100%);
  transform: translateX(100%);
  /* Apply animation to this element */
  -moz-animation: example1 30s linear infinite;
  -webkit-animation: example1 30s linear infinite;
  animation: example1 30s linear infinite;
  /* background-color: rgb(61, 61, 61); */
}

.example1 p:nth-child(2) {
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
  -moz-transform: translateX(100%);
  -webkit-transform: translateX(100%);
  transform: translateX(100%);
  /* Apply animation to this element */
  -moz-animation: example1 15s linear infinite;
  -webkit-animation: example1 15s linear infinite;
  animation: example1 15s linear infinite;
  /* background-color: rgb(61, 61, 61); */
}
.example1 p:nth-child(3) {
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
  -moz-transform: translateX(100%);
  -webkit-transform: translateX(100%);
  transform: translateX(100%);
  /* Apply animation to this element */
  -moz-animation: example1 20s linear infinite;
  -webkit-animation: example1 20s linear infinite;
  animation: example1 20s linear infinite;
  /* background-color: rgb(61, 61, 61); */
}
.example1 p:nth-child(4) {
  font-size: 3em;
  color: rgb(122, 122, 122);
  position: absolute;
  width: 200%;
  top: 3%;
  /* height: 100%; */
  margin: 0;
  line-height: 50px;
  text-align: center;
  /* Starting position */
  -moz-transform: translateX(100%);
  -webkit-transform: translateX(100%);
  transform: translateX(100%);
  /* Apply animation to this element */
  -moz-animation: example1 20s linear infinite;
  -webkit-animation: example1 20s linear infinite;
  animation: example1 20s linear infinite;
  /* background-color: rgb(61, 61, 61); */
}
/* Move it (define the animation) */
@-moz-keyframes example1 {
  0% {
    -moz-transform: translateX(100%);
  }
  100% {
    -moz-transform: translateX(-100%);
  }
}
@-webkit-keyframes example1 {
  0% {
    -webkit-transform: translateX(100%);
  }
  100% {
    -webkit-transform: translateX(-100%);
  }
}
@keyframes example1 {
  0% {
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
.example1:before,
.example1:after {
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
