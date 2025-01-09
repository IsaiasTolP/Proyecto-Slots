<template>
    <div class="crime-scene">
      <slot />
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  
  export default defineComponent({
    name: 'CrimeScene',
  });
  </script>
  
  <style scoped>
  .crime-scene {
    border: 2px dashed #8b0000;
    padding: 20px;
    background-color: #f5f5f5;
    border-radius: 10px;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
    color: #333;
    font-family: 'Arial', sans-serif;
  }
  </style>