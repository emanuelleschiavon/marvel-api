<template>
  <div id="tabela-personagens">
    <table>
       <th>Nome</th>
       <th>Descriçao</th>
       <th>Detalhes</th>
      <td>
        <tr v-for="personagem in personagens">{{ personagem.nome }}</tr>
      </td>
      <td>
        <tr v-for="personagem in personagens">{{ personagem.descricao }}</tr>
      </td>
    </table>


  </div>
</template>

<script>
var app = new Vue({
  el: '#tabela-personagens',
  data: {
    personagens: [
      { nome: 'Demolidor', descricao: 'Cego' },
      { nome: 'Miss Marvel', descricao: 'Voa' },
      { nome: 'Viuva Negra', descricao: 'Espia' },
      { nome: 'Hulk', descricao: 'Verde' },
      { nome: 'Homem de Ferro', descricao: 'Rico' },
    ]
  }
})

</script>

<style>

</style>
