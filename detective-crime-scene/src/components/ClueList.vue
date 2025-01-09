<template>
    <div>
      <ul class="clue-list">
        <slot name="clue" v-for="clue in sortedClues" :clue="clue" :key="clue.name" />
      </ul>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent, PropType } from 'vue';
  
  interface Clue {
    name: string;
    importance: number;
  }
  
  export default defineComponent({
    name: 'ClueList',
    props: {
      clues: {
        type: Array as PropType<Clue[]>,
        required: true,
      },
    },
    computed: {
      sortedClues() {
        return this.clues.sort((a, b) => b.importance - a.importance);
      },
    },
  });
  </script>
  
  <style scoped>
  .clue-list {
    list-style-type: none;
    padding: 0;
    margin: 10px 0;
  }
  .clue-list li {
    padding: 10px;
    margin: 5px 0;
    border: 1px solid #444;
    border-radius: 5px;
    background: #fff;
    color: #000;
    font-family: 'Courier New', Courier, monospace;
  }
  </style>