<script setup lang="ts">
import { ref } from 'vue';
import Tag from './Tag.vue';

interface IngredienteSelecionavelProps {
  ingrediente: string
  ativa?: boolean
}

const props = defineProps<IngredienteSelecionavelProps>();

const emit = defineEmits<{
  (event: 'adicionarIngrediente', ingrediente: string): void;
  (event: 'removerIngrediente', ingrediente: string): void;
}>();

const selecionado = ref(false)

const aoClicar = () => {
  selecionado.value = !selecionado.value

  if (selecionado.value) {
    emit('adicionarIngrediente', props.ingrediente);
  } else {
    emit('removerIngrediente', props.ingrediente);
  }
}

</script>

<template>
  <button
    class="ingrediente"
    v-on:click="aoClicar"
    :aria-pressed="selecionado"
  >
    <Tag :texto="props.ingrediente" :ativa="selecionado"/>
  </button>
</template>

<style scoped>
.ingrediente {
  cursor: pointer;
}
</style>