<template>
  <v-card
    title="Candidate commands:"
    class="candidatecommand"
    scrollable
    outlined
  >
    <v-card-text >
      <Candidates
        ref="candidates"
        @selected="(command) => emits('selected', command)"
      />
    </v-card-text>
  </v-card>
</template>

<script setup>
  import Candidates from '@/components/Candidates.vue'
  import { ref } from 'vue';

  const candidates = ref();
  const emits = defineEmits(['selected']);

  const setTarget = (id) => {
    candidates.value.setTarget(id);
  };

  const setTerminal = (id) => {
    candidates.value.setTerminal(id);
  };

  defineExpose({
    setTarget,
    setTerminal,
  });
</script>
