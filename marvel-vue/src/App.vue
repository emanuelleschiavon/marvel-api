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

const baseUrl = 'https://gateway.marvel.com:443/v1/public'
const apiKey = '1bf4c8e588d3f4faf897acf7b5ade1d5'

const listarPersonagens = () => {
  axios.get(`${baseUrl}/characters`, {
      params: {
        apikey: apiKey
      }
    })
    .then(function (response) {
      return response.data.map((char) => {
        return {
          name: char.name,
          descricao: char.description,
          imagem: char.thumbnail.path
        }
      });
    })
    .catch(function (error) {
      console.log(error);
    });
}

const listarQuadrinhos = () => {
  
}

const quadrinhoPorNome = (nome) => {
  
}

export default {
  name: "tabela-personagens",
  data() {
    return {
     personagens : listarPersonagens()
    }
  }
  
}
</script>

<style>

</style>
