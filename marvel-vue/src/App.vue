<template>
  <div id="tabela-personagem">
    <table class="table table-bordered">
      <thead>
       <th>Nome</th>
       <th>Descriçao</th>
       <th>Detalhes</th>
      </thead>
      <tbody>
      <td>
        <tr v-for="personagem in personagens" :key="personagem.nome">{{ personagem.nome }}</tr>
      </td>
      <td>
        <tr v-for="personagem in personagens" :key="personagem.nome">{{ personagem.descricao }}</tr>
      </td>
      <td></td>
    </tbody>
  </table>
  </div>
</template>

<script>
export default {
  name: "tabela-personagens",
  data() {
    return {
      personagens: [
        { nome: "Demolidor", descricao: "Cego" },
        { nome: "Miss Marvel", descricao: "Voa" },
        { nome: "Viuva Negra", descricao: "Espia" },
        { nome: "Hulk", descricao: "Verde" },
        { nome: "Homem de Ferro", descricao: "Rico" }
      ]
    };
  }
};
</script>

<style>

</style>
