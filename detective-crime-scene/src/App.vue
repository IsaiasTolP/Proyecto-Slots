<template>
  <div id="app">
    <CrimeScene>
      <template #default>
        <h1>Escena del Crimen</h1>
        <ClueList :clues="clues" @resolve="resolveCase">
          <template #clue="{ clue }">
            <li>{{ clue.name }} - Nivel: {{ clue.importance }}</li>
          </template>
        </ClueList>
        <DialogueBox>
          <template #header>
            <h2>Diálogo</h2>
          </template>
          <template #body>
            <p>Detective: ¿Qué viste?</p>
            <p>Testigo: Vi un vaso roto y un sobre sospechoso.</p>
          </template>
          <template #footer>
            <button @click="resolveCase">Resolver el caso</button>
          </template>
        </DialogueBox>
      </template>
    </CrimeScene>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import CrimeScene from './components/CrimeScene.vue';
import ClueList from './components/ClueList.vue';
import DialogueBox from './components/DialogueBox.vue';

export default defineComponent({
  name: 'App',
  components: { CrimeScene, ClueList, DialogueBox },
  setup() {
    const clues = ref([
      { name: 'Huellas', importance: 3 },
      { name: 'Vaso roto', importance: 2 },
      { name: 'Sobre sospechoso', importance: 5 },
    ]);

    const resolveCase = () => {
      const importantClues = clues.value.filter((clue) => clue.importance >= 3);
      if (importantClues.length / clues.value.length > 0.6) {
        alert('¡Enhorabuena! Has resuelto el caso.');
      } else {
        alert('No has acertado, inténtalo de nuevo.');
      }
    };

    return { clues, resolveCase };
  },
});
</script>