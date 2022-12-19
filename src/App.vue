<template>
  
   <main>
      <div class="lg:bg-white w-[375px] lg:mx-auto h-screen flex flex-col 
            lg:w-[1200px] lg:max-h-[770px] lg:flex-row shadow-xl rounded-xl">
         <nav-main></nav-main>
         <page-main class="mx-5 lg:mx-8"></page-main>
      </div>
      <div class="attribution">
         Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>. 
         Coded by <a href="#">R. Morgen</a>.
      </div>
   </main>
</template>

<script setup>
   import {useWindowResize} from '../../use/hooks.js' 
   import store from "./store.js"

   const { width, height } = useWindowResize(); 
   store.wWidth=width  
   store.wHeight=height 
  
</script>


<style>
   #app {
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      font-family: 'Ubuntu';
   }
   body:not(.tab-user) button:focus,
   body:not(.tab-user) input:focus,
   body:not(.tab-user) select:focus,
   body:not(.tab-user) textarea:focus {
      outline: none;
   }
</style>
