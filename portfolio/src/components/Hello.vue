<template>
  <!-- <h1 class=" text-white text-[5rem]">Привет, я Айнур</h1> -->
  <section class="container">
  <h1>
    <span class="title">This is</span>
    <span class="title">a long</span>
    <span class="title">long title</span>
  </h1>
  
  <div class="button">restart</div>
</section>
</template>


<script lang="ts">
  export default {

  }
</script>


<style scoped>
:root {
  --shadow: #533d4a;
  --text-color: white;
}
@import url(https://fonts.googleapis.com/css?family=Fjalla+One);

html{
  height: 100%;
}

body{
  font-family: 'Fjalla One', sans-serif;
  background: black;
}

.container{
  /* transform: translate(-50%, -50%); */
  /* top: 50%;
  left: 50%; */
  /* display: block; */
  /* position: absolute; */
  max-width: 225px;
}

.button{
  float: left;
  position: relative;
  bottom: -65px;
  left: 50%;
  transform: translateX(-50%) rotate(-10deg);
  color: white;
  text-transform: uppercase;
  opacity: 0;
  visibility: hidden;
  cursor: pointer;
}
  
.button  span{
    transform: skew(-10deg);
    display: block;
    float: left;
    text-shadow: var(--shadow) 1px 1px, var(--shadow) 2px 2px, var(--shadow) 3px 3px, var(--shadow) 4px 4px;
  }

h1{
  color: #fff;
  text-transform: uppercase;
  font-size: 42px;
  margin: 0;
  line-height: 47px;
  letter-spacing: 2px;
}

.title{
  transform: translateX(-50%) rotate(-10deg);
  display: block;
  float: left;
  left: 50%;
  position: relative;
  color: white;
  
}
span {
    transform: skew(-20deg);
    display: block;
    float: left;
    text-shadow: var(--shadow) 1px 1px, var(--shadow) 2px 2px, var(--shadow) 3px 3px, var(--shadow) 4px 4px, var(--shadow) 5px 5px, var(--shadow) 6px 6px;
    min-width: 10px;
    min-height: 10px;
    position: relative;
  }

</style>
