<script setup>
import { computed, ref } from 'vue';
defineProps({
    dadosEdit: {
        type: Object,
        required: true
    }
})

const nomeBotao = computed(() => {
    return botao.value ? 'Esconder' : 'Mostrar';
});
const botao = ref(false)

</script>

<template>
    <div class="container">
        <div class="formulario">
            <form @submit.prevent="mostrarResultado = !mostrarResultado">
                <div class="title">
                    <h1>Formulário</h1>
                </div>
                <div class="row">
                    <input type="text" v-model="dadosEdit.nome" required placeholder="Nome:">
                </div>
                <div class="row">
                    <input type="email" v-model="dadosEdit.email" placeholder="Email:">
                </div>
                <div class="row">
                    <input type="password" v-model="dadosEdit.senha" placeholder="Senha:">
                </div>
                <div class="row">
                    <input type="password" v-model="dadosEdit.confsenha" placeholder="Confirmar Senha:">
                </div>
                <div class="row">
                    <input type="date" v-model="dadosEdit.data" placeholder="Data de Nascimento:">
                </div>
                <div class="row">
                    <label for="">Endereço:</label>
                </div>
                <div class="row">
                    <input type="text" v-model="dadosEdit.rua" placeholder="Rua">
                </div>
                <div class="row">
                    <input type="text" v-model="dadosEdit.numero" placeholder="Número">
                </div>
                <div class="row">
                    <input type="text" v-model="dadosEdit.bairro" placeholder="Bairro">
                </div>
                <div class="row">
                    <input type="text" v-model="dadosEdit.cidade" placeholder="Cidade">
                </div>
                <div class="row">
                    <input type="number" v-model="dadosEdit.cep" placeholder="Cep">
                </div>
                <div class="row">
                    <label for="">Estados:</label>
                    <select v-model="dadosEdit.estado">
                        <option value="AC">ACRE</option>
                        <option value="AL">ALAGOAS</option>
                        <option value="AP">AMAPÁ</option>
                        <option value="AM">AMAZONAS</option>
                        <option value="BA">BAHIA</option>
                        <option value="CE">CEARÁ</option>
                        <option value="DF">DISTRITO FEDERAL</option>
                        <option value="ES">ESPÍRITO SANTO</option>
                        <option value="GO">GOIÁS</option>
                        <option value="MA">MARANHÃO</option>
                        <option value="MT">MATO GROSSO</option>
                        <option value="MS">MATO GROSSO DO SUL</option>
                        <option value="MG">MINAS GERAIS</option>
                        <option value="PA">PÁRA</option>
                        <option value="PB">PARAÍBA</option>
                        <option value="PR">PARANÁ</option>
                        <option value="PB">PERNAMBUCO</option>
                        <option value="PI">PIAUÍ</option>
                        <option value="RJ">RIO DE JANEIRO</option>
                        <option value="RN">RIO GRANDE DO NORTE</option>
                        <option value="RS">RIO GRANDE DO SUS</option>
                        <option value="RO">RONDÔNIA</option>
                        <option value="RR">RORAIMA</option>
                        <option value="SC">SANTA CATARINA</option>
                        <option value="SP">SÃO PAULO</option>
                        <option value="SE">SERGIPE</option>
                        <option value="TO">TOCANTINS</option>
                    </select>
                </div>

                <div class="row">
                    <label for="">Linguagem de Programação</label>
                    <div class="bglh">
                        <div class="checkbox">
                            <input type="radio" value="C++" v-model="dadosEdit.linguas" id="" />
                            <p>C++</p>
                        </div>
                        <div class="checkbox">
                            <input type="radio" value="Python" v-model="dadosEdit.linguas" id="" />
                            <p>Python</p>
                        </div>
                        <div class="checkbox">
                            <input type="radio" value="JavaScript" v-model="dadosEdit.linguas" id="" />
                            <p>JavaScript</p>
                        </div>
                        <div class="checkbox">
                            <input type="radio" value="Java" v-model="dadosEdit.linguas" id="" />
                            <p>Java</p>
                        </div>
                    </div>
                </div>
                <div class="row">
                    <label for="">Hobbies favoritos</label>
                    <div class="bglh">
                        <div class="checkbox">
                            <input type="checkbox" v-model="dadosEdit.hobbies" value="Música" id="" />
                            <p>Musica</p>
                        </div>
                        <div class="checkbox">
                            <input type="checkbox" v-model="dadosEdit.hobbies" value="Esportes" id="" />
                            <p>Esportes</p>
                        </div>
                        <div class="checkbox">
                            <input type="checkbox" v-model="dadosEdit.hobbies" value="Viagem" id="" />
                            <p>Viagem</p>
                        </div>
                        <div class="checkbox">
                            <input type="checkbox" v-model="dadosEdit.hobbies" value="Cozinha" id="" />
                            <p>Cozinhar</p>
                        </div>
                    </div>
                </div>
                <div class="row">
                    <input type="text" v-model="biografia" id="" placeholder="Biografia:" />
                </div>
                <div class="button">
                    <button @click="botao = !botao">{{ nomeBotao }}</button>
                </div>
            </form>
        </div>
    </div>
</template>

<style scoped>
* {
    padding: 0;
    margin: 0;
    border: 0;
    box-sizing: border-box;
}

.container {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 1.5rem;
    background-image: linear-gradient(to left, #1e2124, #282b30, #424549, #424549);
}

.formulario,
.resultado {
    padding: 20px;
    display: flex;
    flex-direction: column;
}

.formulario {
    background-color: #1e2124;
    justify-content: center;
    align-items: center;
}

h1 {
    color: #fff;
}

.resultado {
    background-color: #7289da;
    width: 500px;
    justify-content: center;
    align-items: start;
    animation: spin 2s ease;
    animation-iteration-count: 1;
    gap: 10px;
}

.formulario .row {
    margin: 10px 0px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    text-align: center;
}

.formulario .row input {
    padding: 10px;
    border-radius: 0;
    border: 2px solid transparent;
    width: 100%;
}

.formulario .row input:hover {
    padding: 10px;
    border-radius: 0;
    border: 2px solid #7289da;
}



.checkbox {
    display: flex;
    align-items: center;
    justify-content: space-around;
    width: 100px;
}

.bglh {
    display: flex;
}

label {
    font-size: 1.5rem;
    color: #fff;
}

select {
    padding: 10px;
    color: #fff;
}

.title {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}

p {
    color: #fff;
}

.button {
    display: flex;
    justify-content: end;
    align-items: center;
}
</style>
