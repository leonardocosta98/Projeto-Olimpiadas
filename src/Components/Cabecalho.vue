<template>
    <header>
        <div id="cabecalho">
            <img class="logotipo" :src="logotipo" alt="Logotipo">
            <nav class="cabecalho-nav" v-if="obterRotaAtual()!='/'">
                <Botao textoDoBotao="Login" link="/" class="cabecalho-botao"/>
                <Botao textoDoBotao="Postagens" link="/Areapostagem" class="cabecalho-botao"/>
                <Botao textoDoBotao="Sair" @click="fecharSite" class="cabecalho-botao"/>
                <p v-if="usuario" class="usuario-bemvindo">Bem-vindo, {{usuario}}</p>
            </nav>
        </div>
    </header>
</template>

<script>
import Botao from './Botao.vue';
export default {
    name: "Cabecalho",
    props: {
        logotipo: String,
        usuario: String,
    },
    components: {
        Botao
    },
    methods: {
        obterRotaAtual() {
            console.log(this.$route.path);
            return this.$route.path;
        },
        fecharSite() {
            // Tenta fechar a aba do navegador
            window.close();
        }
    }
}
</script>

<style scoped>
header {
    background-color: #ffffff;
    padding: 20px 0; 
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); 
    border-radius: 10px 10px 10px;
    box-shadow: 5px 5px 5px 5px;
}

#cabecalho {
    display: flex; 
    justify-content: space-between;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px; 
}

.logotipo {
    height: 100px; 
    border-radius: 10px;
}

.cabecalho-nav {
    display: flex;
    align-items: center;
}

.cabecalho-botao {
    margin-left: 20px;
    background-color: #ffffff;
    color: white; 
    padding: 10px 20px;
    border: none; 
    border-radius: 5px;
    cursor: pointer;
    transition:  0.3s,  0.3s; 
}

.cabecalho-botao:hover {
    transform: translateY(-2px);
}

.usuario-bemvindo {
    margin-left: 20px; 
    color: #000000; 
    font-weight: bold; 
    font-size: 16px; 
}
</style>