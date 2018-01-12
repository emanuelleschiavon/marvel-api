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
export default {
  name: 'tabela-personagens',
  data () {
    return {
        personagens: [
        { nome: 'Demolidor', descricao: 'Cego' },
        { nome: 'Miss Marvel', descricao: 'Voa' },
        { nome: 'Viuva Negra', descricao: 'Espia' },
        { nome: 'Hulk', descricao: 'Verde' },
        { nome: 'Homem de Ferro', descricao: 'Rico' }]
    }
  }
}
</script>

<style>
</style>
