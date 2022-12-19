<template>
   <!--
   <rmInput controlType="textarea" v-model='inpValue' rows='3' />  
   <rmInput v-model='inpValue' />
   <rmInput v-model="inpValue" type="Number">Test</rmInput>
   -->
   <div class="w-full">
      <label :for="inpId" class="label " >
         <slot></slot>
      </label>
      <input v-if="controlType === 'input'"
         :id="inpId"
         class="rm-Input"
         :type="type"
         :value="modelValue"
         @blur="$emit('update:modelValue', $event.target.value)"
      />
      <textarea v-if="controlType === 'textarea'"
         :id="inpId"
         class="rm-Input"
         :rows="rows"
         :value="modelValue"
         @blur="$emit('update:modelValue', $event.target.value)"
      ></textarea>
   </div>
</template>

<script setup>
   import {useRandom} from '/Users/rainermorgen/MEGA/Server/use/hooks.js' 
   import { onMounted, ref } from 'vue'

   defineEmits(['update:modelValue'])
   defineProps({
      type:{
         type: String,
         default: 'text'
      },
      modelValue:{
         type: String,
         default: ''
      },
      controlType:{
         type: String,
         default: 'input'
      },
      rows: {
         type: String,
         default: "5"
      }
   })

   const inpId=ref()
   onMounted(() => {
      inpId.value='ip'+ useRandom()
   })

</script>


<style  scoped>
   /* Chrome, Safari, Edge, Opera */
   input::-webkit-outer-spin-button,
   input::-webkit-inner-spin-button {
      -webkit-appearance: none;
      margin: 0;
   }

   /* Firefox */
   input[type=number] {
      -moz-appearance: textfield;
   }
   .rm-Input{
      /* @apply bg-gray-50 border border-gray-300 text-gray-900 transition text-lg rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full; */
      @apply transition  rounded-lg ;

   }
   .label {
      @apply block mb-0.5 text-base font-medium text-gray-800;
   }
</style>