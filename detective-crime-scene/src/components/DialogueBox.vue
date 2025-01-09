<template>
    <div class="dialogue-box">
      <div class="header">
        <slot name="header" />
      </div>
      <div class="body">
        <slot name="body" />
      </div>
      <div class="footer">
        <slot name="footer" />
      </div>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  
  export default defineComponent({
    name: 'DialogueBox',
  });
  </script>
  
  <style scoped>
  .dialogue-box {
    border: 2px solid #4682b4;
    padding: 20px;
    background-color: #f0f8ff;
    border-radius: 10px;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.2);
  }
  .header {
    font-weight: bold;
    font-size: 1.2em;
    margin-bottom: 10px;
    color: #2f4f4f;
  }
  .body {
    margin-bottom: 15px;
    line-height: 1.5;
    color: #696969;
  }
  .footer {
    text-align: right;
  }
  .footer button {
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    background-color: #4682b4;
    color: white;
    cursor: pointer;
    font-family: 'Arial', sans-serif;
    font-size: 1em;
  }
  .footer button:hover {
    background-color: #5a9bd4;
  }
  </style>  