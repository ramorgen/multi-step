<template>
   <div class="lg:mx-32 ">
      <add-on-card class="mt-6 lg:mt-12" :index="1"></add-on-card>
      <add-on-card :index="2"></add-on-card>
      <add-on-card :index="3"></add-on-card>   
   </div>
</template>


<script setup>
   import store from '../store.js'
</script>

