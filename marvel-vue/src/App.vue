<template>
  <div id="tabela-personagens">
    <table class="table table-bordered">
      <thead>
       <th>Nome</th>
       <th>Descriçao</th>
       <th>Detalhes</th>
      </thead>
      <tbody>
      <tr v-for="personagem in personagens" :key="personagem.name">
        <td>{{ personagem.nome }}</td>
        <td>{{ personagem.descricao }}</td>
      </tr>
    </tbody>
  </table>
  </div>
</template>

<script>

const baseUrl = 'https://gateway.marvel.com:443/v1/public'
const apiKey = '1bf4c8e588d3f4faf897acf7b5ade1d5'

const listarQuadrinhos = () => {

}

const quadrinhoPorNome = (nome) => {

}

export default {
  name: "tabela-personagens",
  data() {
    return {
     personagens: []
    }
  },

  created () {
  self = this;
  axios.get(`${baseUrl}/characters`, {
      params: {
        apikey: apiKey
      }
    })
    .then(function (response) {
      console.log(response);
       self.personagens = response.data.data.results.map((char) => {
        return {
          nome: char.name,
          descricao: char.description,
          imagem: char.thumbnail.path
        }
      });
    })
    .catch(function (error) {
      console.log(error);
    });
}

}
</script>

<style>

</style>
