<template>
  <div
    @mouseover="changeSquareHoverState()"
    @mouseleave="changeSquareHoverState()"
    class=" transition duration-500 bg-black w-48 aspect-[5/7] rounded-2xl absolute translate-x-1 rotate-1"
    :class="{
      'scale-105': isHovered,
      '-translate-x-[8rem] translate-y-[1rem] rotate-[-20deg]': isClicked,
      'example1': !img,
    }"
    :style="styles"
  >
    <slot>
        <img
          :src="img"
          alt="spa"
          class="rounded-[inherit] border-2 border-white"
          style=""
        />
    </slot>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const props = defineProps({
  xInitial: Number,
  yInitial: Number,
  rotateInitial: Number,
  x: Number,
  y: Number,
  img: String,
  rotate: Number,
  z: String,
  link: String,
  duration: Number,
  isClicked: Boolean,
  isHovered: Boolean,
});

const isCardHovered = ref(false);



const changeSquareHoverState = () => {
  isCardHovered.value = !isCardHovered.value;
};

const zIndex = computed(() => {
  return props.z ;
});


const translateX = computed(() => {
  return props.isClicked ? props.x : props.xInitial;
});

const translateY = computed(() => {
  return props.isClicked ? props.y :  props.yInitial;
});

const rotate = computed(() => {
  return props.isClicked ? props.rotate : props.rotateInitial;
});


const delay = computed(() => {
  if (props.isClicked && isCardHovered.value) {
    return "0";
  }
  if (props.isClicked && !isCardHovered.value) {
    return "0";
  }

  return props.isClicked ? props.delay : "0";
});

const duration = computed(() => {
  if (props.isClicked && isCardHovered.value) {
    return "0.3";
  }

  return props.isClicked ? props.duration : "1";
});
const hoverScale = computed(() => {
  return isCardHovered.value ? "1.1" : "1";
});

const styles = computed(() => {
  return {
    "z-index": zIndex.value,
    transform: `rotate(${rotate.value}deg) translateX(${translateX.value}rem) translateY(${translateY.value}rem) scale(${hoverScale.value})`,
    "transition-delay": `${delay.value}s`,
    "transition-duration": `${duration.value}s`,
  };
});
</script>

<style scoped>
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
  
