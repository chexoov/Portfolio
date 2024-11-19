<template>
    <div class="absolute ">
      
    
        <div
            @mouseover.capture="changeSquareHoverState()"
            @mouseleave.capture="changeSquareHoverState()"
            id="littleCardGit"
            class="bg-black transition hover:scale-110 squareTransitionFunc duration-[5s]  w-20 aspect-square rounded-xl absolute"
            :class="{
              ' rotate-[8deg] duration-[1s] cursor-pointer ':
                isClicked,
            }"
            :style="styles"
          >
            <a :href="link" target="_blank">
              <img
              
                :src="img"
                class="h-[100%] w-[100%] rounded-xl"
                alt="GitHub"
              />
            </a>
            <p
            v-html="label"
              class="text-white absolute transition translate-x-[-3.8rem] translate-y-[-4rem] opacity-0  z-[-2]"
              :class="{ ' opacity-100': isCardHovered ,  }"
            >
              
            </p>
          </div>
    </div>
</template>

<script setup>
import { ref, computed } from 'vue'
const props =defineProps({
    delay: Number,
    x: Number,
    y: Number,
    img: String,
    rotate: Number,
    z: String,
    link: String,
    duration: Number,
    isClicked: Boolean,
    label: String,
})



const isCardHovered = ref(false)

const changeSquareHoverState = () => {
    
    isCardHovered.value = !isCardHovered.value
}

const zIndex = computed(() => {
    return props.isClicked ? props.z : '0'
})

const translateX = computed(() => {
    return props.isClicked ? props.x : '0'
})

const translateY = computed(() => {
    return props.isClicked ? props.y : '0'
})

const rotate = computed(() => {
    return props.isClicked ? props.rotate : '0'
})

const delay = computed(() => {
    if(props.isClicked && isCardHovered.value) {
        return '0'
    }
    if(props.isClicked && !isCardHovered.value) {
        return '0'
    }

    return props.isClicked ? props.delay : '0'
})

const duration = computed(() => {
    if(props.isClicked && isCardHovered.value) {
        return '0.3'
    }

    return props.isClicked ? props.duration : '1'
})
const hoverScale = computed(() => {
    return isCardHovered.value ? '1.1' : '1'
})

const styles = computed(() => {
    return {
        'z-index': zIndex.value,
        'transform': `rotate(${rotate.value}deg) translateX(${translateX.value}rem) translateY(${translateY.value}rem) scale(${hoverScale.value})`,
        'transition-delay': `${delay.value}s`,
        'transition-duration': `${duration.value}s`,
        // 'width': `${hoverScale.value}rem`,
    }
})
</script>