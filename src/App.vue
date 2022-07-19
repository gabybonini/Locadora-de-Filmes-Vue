<template>
  <div class="container">
    <h1>Bem vindo a {{ title }}</h1>
  </div>
  <div class="horas">
    <p v-if="horas >= 12 && horas < 21" id="aberta">Está Aberta!</p>
    <p v-else-if="horas >= 22 && horas < 23" id="proximo-fechar">Próxima de Fechar!</p>
    <p v-else id="fechada">Está Fechada!</p>
  </div>

  <div class="row">
    <div class="col">
      <h2>Filmes encontrados</h2>
    </div>
  </div>

  <div class="row">

    <div class="col-3" v-bind:key="filme.id" v-for="filme in filmes">
      <div class="card">
        <img v-bind:src="filme.imagem" class="card-img-top" alt="Imagem do filme">
        <div class="card-body">
          <h5 class="card-title">{{ filme.titulo }}</h5>
          <p class="card-text">{{ filme.descricao }}</p>
          <p class="card-text">{{ filme.valor }}</p>
          <a href="#" class="btn btn-primary">ALUGAR</a>
        </div>
      </div>
    </div>

  </div>

</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data() {
    return {
      title: "Locadora de Filmes",
      horas: new Date().getHours(),
      filmes: [
        { id: 1, titulo: "Avatar: The Way of Water", descricao: "Jake Sully vive com sua nova família formada no planeta Pandora. " +
              "Uma vez que uma ameaça familiar retorna para terminar o que foi iniciado anteriormente, Jake deve trabalhar com" +
              " Neytiri e o exército da raça Na'vi para proteger seu planeta",
          valor: "INDISPONÍVEL", imagem: "https://lumiere-a.akamaihd.net/v1/images/poster-avatar-2-bra_96b8c77c.png?region=0,0,864,1280"},

        { id: 2, titulo: "Pantera-Negra: Wakanda Forever", descricao: "Conheça a história de T'Challa, príncipe do reino" +
              " de Wakanda, que perde o seu pai e viaja para os Estados Unidos, onde tem contato com os Vingadores." +
              " Entre as suas habilidades estão a velocidade, inteligência e os sentidos apurados.",
          valor: "R$ 65,00", imagem: "https://br.web.img2.acsta.net/pictures/17/12/07/16/09/2291532.jpg"},

        { id: 3, titulo: "Viúva Negra", descricao: "Perseguida por uma força que não irá parar até derrotá-la, ela" +
              " terá que lidar com sua antiga vida de espiã, e também reencontrar membros de sua família que deixou para " +
              "trás antes de se tornar parte dos Vingadores.",
          valor: "R$ 45.00", imagem: "https://lumiere-a.akamaihd.net/v1/images/image_a2514f6d.jpeg?region=0%2C0%2C540%2C810"},

        { id: 4, titulo: "Jungle Cruise", descricao: "uma missão pelas densas florestas amazônicas com a intenção de " +
              "encontrar uma misteriosa árvore com poderes de cura que poderá mudar para sempre o futuro da medicina.",
          valor: "R$ 35,00", imagem: "https://lumiere-a.akamaihd.net/v1/images/image_d14ae22d.jpeg?region=0%2C0%2C540%2C810"},

        { id: 5, titulo: "Eternos",  descricao: "Eternos são seres super dotados com características " +
              "como imortalidade e manipulação de energia cósmica,e eles são frutos de experiências" +
              " fracassadas de seu próprio criador, o Celestial Arishem, desde a criação da Terra há milhões de anos.",
          valor: "R$ 25,00", imagem: "https://disneyplusbrasil.com.br/wp-content/uploads/2021/05/Poster-Eternos-Reduzido-691x1024.jpg"},
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#aberta {
  color: blue;
}
#proximo-fechar {
  color: orange;
}
#fechada {
  color: red;
}
.row {
  max-width: 400vh;
  align-items: baseline;
}
</style>
