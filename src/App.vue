<template>
  <div class="flex">
    <Formulario @conteudo="enviarConteudo" />
    <ListaProduto :conteudoObj="conteudoObj" />
  </div>
</template>

<script>
import Formulario from "./components/Formulario.vue";
import ListaProduto from "./components/ListaProduto.vue";

export default {
  name: "App",
  components: {
    Formulario,
    ListaProduto,
  },
  data() {
    return {
      conteudoObj: "",
    };
  },
  methods: {
    enviarConteudo(conteudo) {
      this.conteudoObj = conteudo;
      console.log(this.conteudoObj);
    },
  },
};
</script>

<style>
* {
  padding: 0;
  margin: 0;
  font-family: "Roboto", sans-serif;
}
.flex {
  display: flex;
  justify-content: space-between;
  max-width: 1100px;
  margin: 50px auto;
  padding: 10px;
}
</style>
