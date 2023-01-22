<template>
  <!-- This is a recreation of the SVG animation that can be found on Wokine.com -->

<div class="hello-parent">
  
  <svg class="hello-word" width="365" height="365" viewBox="0 0 365 365">
    
    
    <g id="H-letter">
    <line class="H-left-stroke" x1="17" y1="17" x2="17" y2="104" stroke="#fff" fill="none" stroke-width="34" stroke-linecap="round" />
    <line class="H-mid-stroke" x1="17" y1="17" x2="82" y2="17" stroke="#fff" fill="none" stroke-width="34" stroke-linecap="round"/>
    <line class="H-mid-stroke-delayed" x1="17" y1="62" x2="82" y2="62" stroke="#fff" fill="none" stroke-width="34" stroke-linecap="round" />
    <line class="H-right-stroke" x1="84" y1="17" x2="84" y2="104" stroke="#fff" fill="none" stroke-width="34" stroke-linecap="round" />
    </g>
    <g id="I-letter">
      <circle class="O-stroke-i" cx="138" cy="20" r="5" stroke="#fff" fill="none" stroke-width="20" />
    <line class="I-letter" x1="138" y1="62" x2="138" y2="104" stroke="#fff" fill="none" stroke-width="34" stroke-linecap="round"/>
    </g>
    
    <!-- <g id="E-letter">
      <line class="E-left-stroke" x1="138" y1="0" x2="138" y2="124" stroke="#000" fill="none" stroke-width="34" />
      <line class="E-top-stroke" x1="154" y1="17" x2="201" y2="17" stroke="#000" fill="none" stroke-width="34" />
      <line class="E-mid-stroke" x1="154" y1="62" x2="196" y2="62" stroke="#000" fill="none" stroke-width="34" />
      <line class="E-bottom-stroke" x1="154" y1="107" x2="201" y2="107" stroke="#000" fill="none" stroke-width="34" />
    </g> -->
    
    <g id="L-one-letter">
      <line class="L-one-long-stroke" x1="17" y1="170" x2="17" y2="260" stroke="#fff" fill="none" stroke-width="34" />
      <line class="L-one-short-stroke" x1="20" y1="170" x2="84" y2="260" stroke="#fff" fill="none" stroke-width="34" stroke-linecap="round" />
      <line class="L-one-long-stroke" x1="84" y1="170" x2="84" y2="260" stroke="#fff" fill="none" stroke-width="34" />
    </g>
    
    <g id="L-two-letter">
      <line class="L-two-long-stroke" x1="138" y1="170" x2="138" y2="260" stroke="#fff" fill="none" stroke-width="34" stroke-linecap="round"/>
      <line class="L-two-long-stroke-delayed" x1="205" y1="170" x2="205" y2="260" stroke="#fff" fill="none" stroke-width="34" stroke-linecap="round"/>
      <line class="L-two-short-stroke" x1="140" y1="260" x2="200" y2="260" stroke="#fff" fill="none" stroke-width="34" stroke-linecap="round" />
    </g>
    
    <!-- <g id="O-letter">
      <circle class="O-stroke" cx="231" cy="215" r="48" stroke="#fff" fill="none" stroke-width="31" />
    </g> -->
    <g id="R-letter">
      <line class="R-two-long-stroke" x1="264" y1="153" x2="264" y2="274" stroke="#fff" stroke-width="34"></line>
      <line class="R-long-stroke" x1="331" y1="170" x2="331" y2="213" stroke="#fff" stroke-width="34"></line>
      <line class="R-long-stroke" x1="331" y1="231" x2="331" y2="274" stroke="#fff" stroke-width="34"></line>
      <line class="H-mid-stroke-delayed" x1="264" y1="214" x2="315" y2="214" stroke="#fff" fill="none" stroke-width="34" />
      <line class="H-mid-stroke-delayed" x1="264" y1="170" x2="315" y2="170" stroke="#fff" fill="none" stroke-width="34" />
    </g>
    
    <g id="red-dot">
      <!-- Initially I tried creating a circle but it was harder to manipulate it how I wanted to in CSS so I resorted to using a line trick to make it look like a circle ....
      
      <circle class="red-dot" cx="325" cy="260" r="20" fill="#FF5851" stroke="none" />
  
      -->
      
      <line x1="325" y1="320" x2="325" y2="320" stroke="#FF5851" class="red-dot" />
    </g>
    
    
  </svg>
  </div>
  
</template>


<script lang="ts">
  export default {

  }
</script>


<style scoped>
html, body, .hello-parent {
  height: 100%;
  width: 100%;
  margin: 0;
}

.hello-parent {
  display: flex;
  background: #fff;
  background: -webkit-radial-gradient(#fff, #eaeaea); 
  background: -o-radial-gradient(#fff, #eaeaea); 
  background: -moz-radial-gradient(#fff, #eaeaea);
  background: radial-gradient(#fff, #eaeaea); 
}

.hello-word {
  margin:auto;
  background-color: rgb(0, 0, 0);
  border: #fff 1px solid;
}
/* H Animation */

.H-left-stroke {
  stroke-dasharray: 87px;
  /* stroke-dashoffset: 124; */
  animation: H-left-move 20s ease forwards;
}

.H-mid-stroke-delayed {
  stroke-dasharray: 67px;
  stroke-dashoffset: 67px;
  animation: H-mid-move 20s ease forwards;
  animation-delay: 0.5s;
}
.H-mid-stroke {
  stroke-dasharray: 67px;
  stroke-dashoffset: 67px;
  animation: H-mid-move 20s ease forwards;
}

.H-right-stroke {
  stroke-dasharray: 87px;
  stroke-dashoffset: 104px;
  animation: H-right-move 20s ease forwards;
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

.E-left-stroke {
  stroke-dasharray: 124px;
  stroke-dashoffset: 124px;
  animation: E-left-move 20s ease forwards;
}

.E-top-stroke {
  stroke-dasharray: 47px;
  stroke-dashoffset: 47px;
  animation: E-top-move 10s ease forwards;
}

.E-mid-stroke {
  stroke-dasharray: 42px;
  stroke-dashoffset: 42px;
  animation: E-mid-move 10s ease forwards;
}

.E-bottom-stroke {
  stroke-dasharray: 47px;
  stroke-dashoffset: 47px;
  animation: E-bottom-move 10s ease forwards;
}

@keyframes E-left-move {
  0% {
    stroke-dashoffset: 124px;
  }
  2% {
    stroke-dashoffset: 124px;
  }
  6% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

@keyframes E-top-move {
  0% {
    stroke-dashoffset: 47px;
  }
  6% {
    stroke-dashoffset: 47px;
  }
  11% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

@keyframes E-mid-move {
  0% {
    stroke-dashoffset: 42px;
  }
  8% {
    stroke-dashoffset: 42px;
  }
  13% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

@keyframes E-bottom-move {
  0% {
    stroke-dashoffset: 47px;
  }
  11% {
    stroke-dashoffset: 47px;
  }
  16% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

/* L One Animation */

.L-one-long-stroke {
  /* border-radius: 50px; */
  stroke-dasharray: 90px;
  stroke-dashoffset: 90px;
  stroke-linecap: round;
  animation: L-one-long-move 50s ease forwards;
}

.L-one-short-stroke {
  stroke-dasharray: 100px;
  stroke-dashoffset: 100px;
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

@keyframes L-one-short-move {
  0% {
    stroke-dashoffset: 90px;
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
  animation: L-two-long-move 20s ease forwards;
}

.R-two-long-stroke {
  stroke-dasharray: 121px;
  stroke-dashoffset: 121px;
  animation: R-two-long-move 20s ease forwards;
}

.L-two-long-stroke-delayed {
  stroke-dasharray: 90px;
  stroke-dashoffset: 90px;
  animation: L-two-long-move 20s ease forwards;
  animation-delay: 0.3s;
}

.L-two-short-stroke {
  stroke-dasharray: 60px;
  stroke-dashoffset: 60px;
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
  animation: O-move 20s ease forwards;
}

.O-stroke-i {
  stroke-dasharray: 302px;
  stroke-dashoffset: 302px;
  animation: O-move 50s ease forwards;
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
  stroke-width: 44px;
  stroke-linecap: round;
  animation: red-dot-grow 8s ease-out forwards;
}

@keyframes red-dot-grow {
  0% {
    stroke-width: 0px;
  }
  15% {
    stroke-width: 0px;
  }
  20% {
    stroke-width: 44px;
  }
  100% {
    stroke-width: 44px;
  }
}

.R-long-stroke {
  stroke-dasharray: 43px;
  stroke-dashoffset: 43px;
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

.I-letter {
  stroke-dasharray: 42px;
  stroke-dashoffset: 42px;
  animation: i-move 5s ease forwards;
}

@keyframes i-move {
  0% {
    stroke-dashoffset: 42px;
  }
  30% {
    stroke-dashoffset: 42px;
  }
  40% {
    stroke-dashoffset: 0px;
  }
  100% {
    stroke-dashoffset: 0;
  }
}
</style>
