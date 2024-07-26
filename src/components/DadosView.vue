<script setup>
defineProps(['pessoa']);
</script>

<template>
 <div class="resultado">
      <h2>Resultado</h2>
      <p>Nome: {{ pessoa.nome }}</p>
      <p>Email: {{ pessoa.email }}</p>
      <p>Senha: {{ pessoa.senha }}</p>
      <p>Confirmar Senha: {{ pessoa.confsenha }}</p>
      <p>Data de Nascimento: {{ pessoa.data }}</p>
      <p>Rua: {{ pessoa.rua }}</p>
      <p>Número: {{ pessoa.numero * 1 }}</p>
      <p>Bairro: {{ pessoa.bairro }}</p>
      <p>CEP: {{ pessoa.cep * 1 }}</p>
      <p>Estado: {{ pessoa.estado }}</p>
      <p>Hobbies: {{ pessoa.hobbies }}</p>
      <p>Linguagens: {{ pessoa.linguas }}</p>
    </div>

</template>

<style scoped>
* {
  padding: 0;
  margin: 0;
  border: 0;
  box-sizing: border-box;
}
.resultado {
  padding: 20px;
  display: flex;
  flex-direction: column;
  background-color: #7289da;
  width: 500px;
  justify-content: center;
  align-items: start;
  animation: spin 2s ease;
  animation-iteration-count: 1;
  gap: 10px;
}


@keyframes spin {
  to {
    transform: scale(1) translate(0px) rotate(0deg) translateY(0);
  }

  from {
    transform: scale(250) translate(2000px) rotate(720deg) translateY(1100px);
  }
}

.resultado p {
  font-size: 16px;
}
</style>