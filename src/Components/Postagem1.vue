<script setup>
import PostModelo from './PostModelo.vue';
import investir from '../assets/investir.jpg';
</script>

<template>
  <div class="card">
    <PostModelo 
      titulo="O que é investimento?"  
      :imagem="investir"
      CorpoDoTexto="Investimento é a alocação de dinheiro em ativos com o objetivo de obter retorno econômico no futuro. 
      Esses ativos podem incluir ações, títulos, imóveis, fundos de investimento e outros instrumentos financeiros."
      autor="Feito por Leonardo"
    />
  </div>
</template>

<style scoped>
.card {
  background-color: #e9e9e9;
  border-radius:  10px 10px 10px 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  padding: 20px; 
  margin: 20px; 
  font-size:large; 
  box-shadow:5px 5px 5px 5px;
}
</style>