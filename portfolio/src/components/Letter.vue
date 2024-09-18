<template>
   <g v-if="letter === 'A'" id="H-letter">
          
          <line
            class="H-left-stroke"
            x1="17"
            y1="17"
            x2="17"
            y2="104"
            stroke="#fff"
            fill="none"
            stroke-width="34"
            stroke-linecap="round"
          />
          <line
            class="H-mid-stroke"
            x1="17"
            y1="17"
            x2="82"
            y2="17"
            stroke="#fff"
            fill="none"
            stroke-width="34"
            stroke-linecap="round"
          />
          <!-- <Letter letter="A"></Letter>
          <Letter letter="R"></Letter>
          <Letter letter="T"></Letter>
          <Letter letter="U"></Letter>
          <Letter letter="R"></Letter> -->
          <line
            class="H-mid-stroke-delayed"
            x1="17"
            y1="62"
            x2="82"
            y2="62"
            stroke="#fff"
            fill="none"
            stroke-width="34"
            stroke-linecap="round"
          />
          <line
            class="H-right-stroke"
            x1="84"
            y1="17"
            x2="84"
            y2="104"
            stroke="#fff"
            fill="none"
            stroke-width="34"
            stroke-linecap="round"
          />
        </g>
        <g v-if="letter === 'R'" id="R-letter">
          <line
            class="R-two-long-stroke"
            x1="138"
            y1="1"
            x2="138"
            y2="120"
            stroke="#fff"
            stroke-width="34"
          ></line>
          <!-- нижняя середина -->
          <line
            class="H-mid-stroke-delayed"
            x1="143"
            y1="62"
            x2="193"
            y2="62"
            stroke="#fff"
            fill="none"
            stroke-width="34"
          ></line>
          <line
            class="R-long-stroke"
            x1="208"
            y1="17"
            x2="208"
            y2="60"
            stroke="#fff"
            stroke-width="34"
          ></line>
         
          <line
            class="R-long-stroke"
            x1="210"
            y1="80"
            x2="210"
            y2="120"
            stroke="#fff"
            fill="none"
            stroke-width="34"
          />
          <!-- верхняя середина -->
          <line
            class="H-mid-stroke-delayed"
            x1="150"
            y1="18"
            x2="200"
            y2="18"
            stroke="#fff"
            stroke-width="34"
          ></line>
        </g>
        <!-- <g id="E-letter">
        <line class="E-left-stroke" x1="138" y1="0" x2="138" y2="124" stroke="#000" fill="none" stroke-width="34" />
        <line class="E-top-stroke" x1="154" y1="17" x2="201" y2="17" stroke="#000" fill="none" stroke-width="34" />
        <line class="E-mid-stroke" x1="154" y1="62" x2="196" y2="62" stroke="#000" fill="none" stroke-width="34" />
        <line class="E-bottom-stroke" x1="154" y1="107" x2="201" y2="107" stroke="#000" fill="none" stroke-width="34" />
      </g> -->

      <!-- буква Т -->
        <g v-if="letter === 'T'" id="L-one-letter">
          <line
            class="L-one-long-stroke"
            x1="50"
            y1="190"
            x2="50"
            y2="260"
            stroke="#fff"
            fill="none"
            stroke-width="34"
          />
          <line
            class="H-mid-stroke-delayed"
            x1="43"
            y1="168"
            x2="17"
            y2="168"
            stroke="#fff"
            fill="none"
            stroke-width="34"
            stroke-linecap="round"
          />
          <line
            class="H-mid-stroke-delayed"
            x1="35"
            y1="168"
            x2="83"
            y2="168"
            stroke="#fff"
            fill="none"
            stroke-width="34"
            stroke-linecap="round"
          />
          
          
        </g>

        <g v-if="letter === 'U'" id="L-two-letter">
          <line
            class="L-two-long-stroke"
            x1="138"
            y1="170"
            x2="138"
            y2="260"
            stroke="#fff"
            fill="none"
            stroke-width="34"
            stroke-linecap="round"
          />
          <line
            class="L-two-long-stroke-delayed"
            x1="205"
            y1="170"
            x2="205"
            y2="260"
            stroke="#fff"
            fill="none"
            stroke-width="34"
            stroke-linecap="round"
          />
          <line
            class="L-two-short-stroke"
            x1="140"
            y1="260"
            x2="200"
            y2="260"
            stroke="#fff"
            fill="none"
            stroke-width="34"
            stroke-linecap="round"
          />
        </g>
        <g v-if="letter === 'R'" id="R-letter">
          <line
            class="R-two-long-stroke"
            x1="264"
            y1="153"
            x2="264"
            y2="274"
            stroke="#fff"
            stroke-width="34"
          ></line>
          <line
            class="R-long-stroke"
            x1="331"
            y1="170"
            x2="331"
            y2="213"
            stroke="#fff"
            stroke-width="34"
          ></line>
          <line
            class="R-long-stroke"
            x1="331"
            y1="231"
            x2="331"
            y2="274"
            stroke="#fff"
            stroke-width="34"
          ></line>
          <line
            class="H-mid-stroke-delayed"
            x1="264"
            y1="214"
            x2="315"
            y2="214"
            stroke="#fff"
            fill="none"
            stroke-width="34"
          />
          <line
            class="H-mid-stroke-delayed"
            x1="264"
            y1="170"
            x2="315"
            y2="170"
            stroke="#fff"
            fill="none"
            stroke-width="34"
          />
        </g>
         <!-- кругляшки -->
          <g v-if="letter === 'O'">
              <g id="red-dot">
               <line
                 x1="163"
                 y1="-19"
                 x2="163"
                 y2="-19"
                 stroke="#ff003c"
                 class="red-dot"
               />
             </g>
             <g id="green-dot">
               <line
                 x1="163"
                 y1="-19"
                 x2="163"
                 y2="-19"
                 stroke="#00ff48"
                 stroke-width="33"
                 class="green-dot"
               />
             </g>
             <g id="blue-dot">
               <line
                 x1="163"
                 y1="-19"
                 x2="163"
                 y2="-19"
                 stroke="#0055ff"
                 stroke-width="33"
                 class="blue-dot"
               />
             </g>
             <g id="yellow-dot">
               <line
                 x1="163"
                 y1="-19"
                 x2="163"
                 y2="-19"
                 stroke="#f9f942"
                 stroke-width="33"
                 class="yellow-dot"
               />
             </g>   
          </g>
          
</template>
<script setup>
defineProps({
  letter: String,

})
</script>

<style scoped>

.H-left-stroke {
  stroke-dasharray: 87px;
  /* stroke-dashoffset: 124; */
  -webkit-animation: H-left-move 20s ease forwards;
  animation: H-left-move 20s ease forwards;
}

.H-mid-stroke-delayed {
  stroke-dasharray: 67px;
  stroke-dashoffset: 67px;
  -webkit-animation: H-mid-move 20s ease forwards;
          animation: H-mid-move 20s ease forwards;
  -webkit-animation-delay: 0.5s; 
          animation-delay: 0.5s;
         
}
.H-mid-stroke {
  stroke-dasharray: 67px;
  stroke-dashoffset: 67px;
  -webkit-animation: H-mid-move 20s ease forwards;
  animation: H-mid-move 20s ease forwards;
}

.H-right-stroke {
  stroke-dasharray: 87px;
  stroke-dashoffset: 104px;
  -webkit-animation: H-right-move 20s ease forwards;
  animation: H-right-move 20s ease forwards;
}

@-webkit-keyframes H-left-move {
  0% {
    stroke-dashoffset: 87px;
  }
  5% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

@keyframes H-left-move {
  0% {
    stroke-dashoffset: 87px;
  }
  5% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

@-webkit-keyframes H-mid-move {
  0% {
    stroke-dashoffset: 67px;
  }
  5% {
    stroke-dashoffset: 67px;
  }
  10% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

@keyframes H-mid-move {
  0% {
    stroke-dashoffset: 67px;
  }
  5% {
    stroke-dashoffset: 67px;
  }
  10% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

@-webkit-keyframes H-right-move {
  0% {
    stroke-dashoffset: 87px;
  }
  5% {
    stroke-dashoffset: 87px;
  }
  10% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

@keyframes H-right-move {
  0% {
    stroke-dashoffset: 87px;
  }
  5% {
    stroke-dashoffset: 87px;
  }
  10% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

/* E Animation */













.L-one-long-stroke {
  /* border-radius: 50px; */
  stroke-dasharray: 90px;
  stroke-dashoffset: 90px;
  stroke-linecap: round;
  -webkit-animation: L-one-long-move 50s ease forwards;
  animation: L-one-long-move 50s ease forwards;
}

.L-one-short-stroke {
  stroke-dasharray: 110px;
  stroke-dashoffset: 110px;
  -webkit-animation: L-one-short-move 10s ease forwards;
  animation: L-one-short-move 10s ease forwards;
}


@keyframes L-one-long-move {
  0% {
    stroke-dashoffset: 87px;
  }
  2% {
    stroke-dashoffset: 0px;
  }
  7% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

@-webkit-keyframes L-one-short-move {
  0% {
    stroke-dashoffset: 110px;
  }
  13% {
    stroke-dashoffset: 0px;
  }
  18% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

@keyframes L-one-short-move {
  0% {
    stroke-dashoffset: 110px;
  }
  13% {
    stroke-dashoffset: 0px;
  }
  18% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

/* L Two Animation */

.L-two-long-stroke {
  stroke-dasharray: 90px;
  stroke-dashoffset: 90px;
  -webkit-animation: L-two-long-move 20s ease forwards;
  animation: L-two-long-move 20s ease forwards;
}

.R-two-long-stroke {
  stroke-dasharray: 121px;
  stroke-dashoffset: 121px;
  -webkit-animation: R-two-long-move 20s ease forwards;
          animation: R-two-long-move 20s ease forwards;
}

.L-two-long-stroke-delayed {
  stroke-dasharray: 90px;
  stroke-dashoffset: 90px;
  -webkit-animation: L-two-long-move 20s ease forwards;
  animation: L-two-long-move 20s ease forwards;
  -webkit-animation-delay: 0.3s;
  animation-delay: 0.3s;
}

.L-two-short-stroke {
  stroke-dasharray: 60px;
  stroke-dashoffset: 60px;
  -webkit-animation: L-two-short-move 10s ease forwards;
  animation: L-two-short-move 10s ease forwards;
}



@keyframes L-two-long-move {
  0% {
    stroke-dashoffset: 90px;
  }
  3% {
    stroke-dashoffset: 90px;
  }
  8% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

@-webkit-keyframes R-two-long-move {
  0% {
    stroke-dashoffset: 121px;
  }
  3% {
    stroke-dashoffset: 121px;
  }
  8% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

@keyframes R-two-long-move {
  0% {
    stroke-dashoffset: 121px;
  }
  3% {
    stroke-dashoffset: 121px;
  }
  8% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

@-webkit-keyframes L-two-short-move {
  0% {
    stroke-dashoffset: 60px;
  }
  15% {
    stroke-dashoffset: 60px;
  }
  20% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

@keyframes L-two-short-move {
  0% {
    stroke-dashoffset: 60px;
  }
  15% {
    stroke-dashoffset: 60px;
  }
  20% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

/* O Animation */

.O-stroke {
  stroke-dasharray: 302px;
  stroke-dashoffset: 302px;
  -webkit-animation: O-move 20s ease forwards;
  animation: O-move 20s ease forwards;
}

.O-stroke-i {
  stroke-dasharray: 302px;
  stroke-dashoffset: 302px;
  -webkit-animation: O-move 50s ease forwards;
  animation: O-move 50s ease forwards;
}

@-webkit-keyframes O-move {
  0% {
    stroke-dashoffset: 302px;
  }
  4% {
    stroke-dashoffset: 302px;
  }
  9% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

@keyframes O-move {
  0% {
    stroke-dashoffset: 302px;
  }
  4% {
    stroke-dashoffset: 302px;
  }
  9% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

/* Red Dot Animation */

.red-dot {
  stroke-width: 0px;
  stroke-linecap: round;
  -webkit-animation: red-dot-grow 8s ease-out forwards;
  animation: red-dot-grow 8s ease-out forwards;
  -webkit-animation-delay: 1s;
  animation-delay: 1s;
}

.green-dot {
  stroke-width: 0px;
  stroke-linecap: round;
  -webkit-animation: green-dot-grow 8s ease-out forwards;
  animation: green-dot-grow 8s ease-out forwards;
  -webkit-animation-delay: 1.1s;
  animation-delay: 1.1s;
}

@-webkit-keyframes green-dot-grow {
  0% {
    stroke-width: 0px;
  }
  15% {
    stroke-width: 0px;
  }
  20% {
    stroke-width: 24px;
  }
  100% {
    stroke-width: 24px;
  }
}

@keyframes green-dot-grow {
  0% {
    stroke-width: 0px;
  }
  15% {
    stroke-width: 0px;
  }
  20% {
    stroke-width: 24px;
  }
  100% {
    stroke-width: 24px;
  }
}
.blue-dot {
  stroke-width: 0px;
  stroke-linecap: round;
  -webkit-animation: blue-dot-grow 8s ease-out forwards;
  animation: blue-dot-grow 8s ease-out forwards;
  -webkit-animation-delay: 1.2s;
  animation-delay: 1.2s;
}



@keyframes blue-dot-grow {
  0% {
    stroke-width: 0px;
  }
  15% {
    stroke-width: 0px;
  }
  20% {
    stroke-width: 14px;
  }
  100% {
    stroke-width: 14px;
  }
}
.yellow-dot {
  stroke-width: 0px;
  stroke-linecap: round;
  -webkit-animation: yellow-dot-grow 8s ease-out forwards;
  animation: yellow-dot-grow 8s ease-out forwards;
  -webkit-animation-delay: 1.3s;
  animation-delay: 1.3s;
}



@keyframes yellow-dot-grow {
  0% {
    stroke-width: 0px;
  }
  15% {
    stroke-width: 0px;
  }
  20% {
    stroke-width: 4px;
  }
  100% {
    stroke-width: 4px;
  }
}

@-webkit-keyframes red-dot-grow {
  0% {
    stroke-width: 0px;
  }
  15% {
    stroke-width: 0px;
  }
  20% {
    stroke-width: 34px;
  }
  100% {
    stroke-width: 34px;
  }
}

@keyframes red-dot-grow {
  0% {
    stroke-width: 0px;
  }
  15% {
    stroke-width: 0px;
  }
  20% {
    stroke-width: 34px;
  }
  100% {
    stroke-width: 34px;
  }
}

.R-long-stroke {
  stroke-dasharray: 43px;
  stroke-dashoffset: 43px;
  -webkit-animation: r-two-stroke 2s ease forwards;
          animation: r-two-stroke 2s ease forwards;
}



@keyframes r-two-stroke {
  0% {
    stroke-dashoffset: 43px;
  }
  80% {
    stroke-dashoffset: 10px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}





</style>
