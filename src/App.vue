<script setup>
import { reactive } from 'vue';
import DadosView from './components/DadosView.vue';
import FormView from './components/FormView.vue';

const pessoa = reactive({
  nome: '',
  email: '',
  senha: '',
  confsenha: '',
  estado: '',
  data: '',
  rua: '',
  numero: '',
  bairro: '',
  cidade: '',
  cep: '',
  linguas: '',
  hobbies: [],

})

</script>

<template>
  <div>
  <FormView :dadosEdit="pessoa" />
</div>
  <div>
  <DadosView :pessoa="pessoa"/>
</div>
</template>

<style scoped>
template{
  display: flex;
}
</style>
