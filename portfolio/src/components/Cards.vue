<template>
  <div
    id="cardGroup"
    class="bg-black h-[100%] w-[100%] grid place-items-center"
  >
    <div
      id="littleCard"
      class="bg-[#ffffff27] w-20 aspect-square rounded-xl absolute"
    ></div>
    <div
      id="littleCard"
      class="bg-[#ffffff27] w-20 aspect-square rounded-xl absolute"
    ></div>
    <div
      id="littleCard"
      class="bg-[#ffffff27] w-20 aspect-square rounded-xl absolute"
    ></div>
    <div
      id="littleCard"
      class="bg-[#ffffff27] w-20 aspect-square rounded-xl absolute"
    ></div>
    <div
    class=" transition duration-500 bg-[#0055ff] w-48 aspect-[5/7] rounded-2xl absolute translate-x-1 rotate-1"
    :class="{ 'scale-105': isHovered, 'translate-x-[-8rem] translate-y-[1rem] rotate-[-20deg]': isClicked }"
    @click="changeClickState()"
    @mouseover="changeHoverState()"
    @mouseleave="changeHoverState()"
    ></div>
    <div
    class=" transition duration-500 bg-[#00ff48] w-48 aspect-[5/7] rounded-2xl absolute translate-x-[-1rem] translate-y-2 rotate-[-4deg] shadow-[-20px_10px_20px_rgba(0,0,0,0.25)]"
    :class="{ 'scale-105': isHovered, 'translate-x-[-2rem] translate-y-[0.5rem] rotate-[-7deg]': isClicked }"
    @click="changeClickState()"
    @mouseover="changeHoverState()"
    @mouseleave="changeHoverState()"
    ></div>
    <div
    class=" transition duration-500 bg-[#f9f942] w-48 aspect-[5/7] rounded-2xl absolute translate-x-[-0.5rem] translate-y-2 rotate-[-2deg] shadow-[-20px_10px_20px_rgba(0,0,0,0.25)]"
    :class="{ 'scale-105': isHovered, 'translate-x-[4rem] translate-y-[0.5rem] rotate-[7deg]': isClicked }"
    @click="changeClickState()"
    @mouseover="changeHoverState()"
    @mouseleave="changeHoverState()"
    ></div>
    <div
    class=" transition duration-500 bg-[#ff003c] w-48 aspect-[5/7] rounded-2xl absolute translate-x-1 translate-y-2 rotate-6 shadow-[-20px_10px_20px_rgba(0,0,0,0.25)]"
    :class="{ 'scale-105': isHovered, 'translate-x-[10rem] translate-y-[2rem] rotate-[20deg]': isClicked }"
    @click="changeClickState()"
    @mouseover="changeHoverState()"
    @mouseleave="changeHoverState()"
    ></div>
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      isHovered: false,
      isClicked: false,
    }
  },
  methods: {
    changeHoverState() {
      this.isHovered = !this.isHovered
    },
    changeClickState() {
      this.isClicked = !this.isClicked
    }
  }
}
</script>

<style scoped>
/* #cardGroup:hover > #bigCard:nth-child(1) {
  transform: translateX(-50px);
} */

.move {
  transform: scale(110%);
}

</style>
