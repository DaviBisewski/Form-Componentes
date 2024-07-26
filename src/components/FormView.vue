<script setup>
import { ref, computed, reactive } from 'vue'

const emit = defineEmits(['salvar'])

const perfil = reactive({
    nome: '',
    senha: '',
    confSenha: '',
    nascimento: '',
    email: '',
    cep: '',
    cidade: '',
    estado: '',
    hobbies: [],
    linguagemProg: '',
    biografia: ''
});

const Estados = [
    { uf: 'AC', nome: 'Acre' },
    { uf: 'AL', nome: 'Alagoas' },
    { uf: 'AP', nome: 'Amapá' },
    { uf: 'AM', nome: 'Amazonas' },
    { uf: 'BA', nome: 'Bahia' },
    { uf: 'CE', nome: 'Ceará' },
    { uf: 'DF', nome: 'Distrito Federal' },
    { uf: 'ES', nome: 'Espírito Santo' },
    { uf: 'GO', nome: 'Goiás' },
    { uf: 'MA', nome: 'Maranhão' },
    { uf: 'MT', nome: 'Mato Grosso' },
    { uf: 'MS', nome: 'Mato Grosso do Sul' },
    { uf: 'MG', nome: 'Minas Gerais' },
    { uf: 'PA', nome: 'Pará' },
    { uf: 'PB', nome: 'Paraíba' },
    { uf: 'PR', nome: 'Paraná' },
    { uf: 'PE', nome: 'Pernambuco' },
    { uf: 'PI', nome: 'Piauí' },
    { uf: 'RJ', nome: 'Rio de Janeiro' },
    { uf: 'RN', nome: 'Rio Grande do Norte' },
    { uf: 'RS', nome: 'Rio Grande do Sul' },
    { uf: 'RO', nome: 'Rondônia' },
    { uf: 'RR', nome: 'Roraima' },
    { uf: 'SC', nome: 'Santa Catarina' },
    { uf: 'SP', nome: 'São Paulo' },
    { uf: 'SE', nome: 'Sergipe' },
    { uf: 'TO', nome: 'Tocantins' }
]
const botao = ref(false)

const nomeBotao = computed(() => {
    return botao.value ? 'Esconder' : 'Mostrar';
});

function enviar(dados) {

    emit('salvar', dados)
}

</script>
<template>
    <main class="formulario">
        <form @submit.prevent="">
            <h1>Formulário</h1>
            <div class="input">
                <label for="nome">Nome</label>
                <input type="text" v-model.trim="perfil.nome" placeholder="Digite seu nome" id="inputName" required />
            </div>
            <div class="input">
                <label for="Email">Email</label>
                <input id="Email" type="email" v-model.trim="perfil.email" placeholder="Digite seu email" required>
            </div>
            <div class="input">
                <label for="Senha">Senha</label>
                <input id="Senha" type="password" v-model.trim="perfil.senha" placeholder="Digite sua Senha" required>
            </div>
            <div class="input">
                <label for="ConSenha">Confirmar Senha</label>
                <input id="ConSenha" type="password" v-model.trim="perfil.confSenha" placeholder="Confirme sua Senha"
                    required>
            </div>
            <div class="input">
                <label for="nascimento">Nascimento</label>
                <input id="nascimento" type="date" v-model="perfil.nascimento" placeholder="Digite sua Nascimento "
                    required>
            </div>
            <div class="input">
                <label for="cep">CEP</label>
                <input id="cep" type="number" v-model="perfil.cep" placeholder="Digite seu CEP" required>
            </div>
            <div class="input">
                <label for="inputCity">Cidade</label>
                <input id="inputCity" type="text" v-model="perfil.cidade" placeholder="Digite sua Cidade" required>
            </div>
            <div class="input">
                <label for="Estado">Estado</label>

                <select id="Estado" value="Estado" v-model="perfil.estado" required>
                    <option v-for="Estado of Estados" :key="Estado.uf" :value="Estado.uf">
                        {{ Estado.nome }}
                    </option>
                </select>
            </div>
            <div>
                <p class="titulo">Hobbies:</p>
                <input type="checkbox" id="esportes" value="Esporte" v-model="perfil.hobbies">
                <label for="esportes">Esportes</label>

                <input type="checkbox" id="viagens" value="Viagens" v-model="perfil.hobbies">
                <label for="viagens">Viagens</label>

                <input type="checkbox" id="musicas" value="Música" v-model="perfil.hobbies">
                <label for="musicas">Músicas</label>

                <input type="checkbox" id="leitura" value="Leitura" v-model="perfil.hobbies">
                <label for="leitura">Leitura</label>

                <input type="checkbox" id="videogame" value="VIdeoGame" v-model="perfil.hobbies">
                <label for="videogame">Video Game</label>
            </div>
            <div>
                <p class="titulo">Linguagem preferida:</p>
                <input type="radio" id="Js" value="JavaScript" v-model="perfil.linguagemProg">
                <label for="Js">JavaScript</label>

                <input type="radio" id="Java" value="Java" v-model="perfil.linguagemProg">
                <label for="Java">Java</label>

                <input type="radio" id="C" value="C" v-model="perfil.linguagemProg">
                <label for="C">C</label>

                <input type="radio" id="Py" value="Python" v-model="perfil.linguagemProg">
                <label for="Py">Python</label>

                <input type="radio" id="C#" value="C#" v-model="perfil.LinguagemProg">
                <label for="C#">C#</label>
            </div>
            <div class="input">
                <label for="bio">Biografia</label>
                <textarea type="text" id="bio" placeholder="Sua Biografia" v-model="perfil.biografia"></textarea>
            </div>
            <div class="button">
                <button @click="enviar(perfil)" type="submit">{{ nomeBotao }}</button>
            </div>
        </form>
    </main>
</template>
<style scoped>
* {
    padding: 0;
    margin: 0;
    border: 0;
    box-sizing: border-box;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

.formulario {
    background-color: #0d0d0d;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 50px;
    border-radius: 20px;
    color: #fff;
}

form {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    gap: 7px;
}

.formulario form h1 {
    font-size: 50px;
    border-bottom: 1px solid #fff;
    margin: 0 0 10px 0;
}

.formulario form .input {
    display: flex;
    justify-content: start;
    align-items: center;
    gap: 15px;
}

.formulario form .input input {
    padding: 2.5px;
    border-radius: 7px;
}

.formulario form .button {
    display: flex;
    justify-content: end;
    align-items: center;
}

.formulario form .button button {
    padding: 5px;
    border-radius: 10px;
}
</style>