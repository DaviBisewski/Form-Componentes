<script setup>
import { computed, reactive, ref } from 'vue';
import FormView from '@/components/FormView.vue';
import DadosView from '@/components/DadosView.vue';

const dados = ref('')

function salvar(item) {
  console.log(item)
  dados.value = item
}

const mostrarDados = computed(() => {
  return dados.value !== ''
})

</script>

<template>
  <div>
    <FormView @salvar="salvar" />
  </div>
  <div>
    <DadosView v-if="mostrarDados" :dadosEdit="dados" />
  </div>
</template>

<style scoped>
div{
  margin: 0 50px;
}
</style>
