<script setup>
import { reactive } from 'vue'
const props = defineProps({
    dadosEdit: {
        type: Object,
        required: true
    }
})

console.log(props.dadosEdit)

</script>
<template>
    <div class="resultado">
        <div class="mainResultados">
            <h1>Resultado</h1>
            <p>Nome: {{ props.dadosEdit.nome }}</p>
            <p>Nascimento: {{ props.dadosEdit.nascimento }}</p>
            <p>Email: {{ props.dadosEdit.email }}</p>
            <p>Cidade: {{ props.dadosEdit.cidade }}</p>
            <p>Estado: {{ props.dadosEdit.estado }}</p>
            <p>Hobbies: {{ props.dadosEdit.hobbies }}</p>
            <p>Linguagem Preferida: {{ props.dadosEdit.linguagemProg }}</p>
            <div class="mainResultados">
                <p> Biografia: {{ props.dadosEdit.biografia }}</p>
            </div>
        </div>
    </div>
</template>
<style scoped>
.resultado {
    background-color: #fff;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    padding: 50px;
    border-radius: 20px;
    gap: 40px;
    border: 1.5px solid #0d0d0d;
    color: #0d0d0d;
    animation: spin 2s ease;
    animation-iteration-count: 1;
}

.resultado h1 {
    font-size: 50px;
    border-bottom: 1px solid #0d0d0d;
    margin: 0 0 10px 0;
}

@keyframes spin {
    to {
        transform: scale(1) translate(0px) rotate(0deg) translateY(0);
    }

    from {
        transform: scale(250) translate(2000px) rotate(720deg) translateY(1100px);
    }
}
</style>
