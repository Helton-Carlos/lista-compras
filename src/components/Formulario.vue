<template>
  <form class="fundo" @submit.prevent="previewFiles()">
    <div class="container">
      <h3>Lista de compras</h3>
      <input type="text" v-model="produto" placeholder="Nome do produto" />
      <p Style="color:red" v-show="mensagem">O nome é obrigatório</p>
      <input type="number" v-model="quantidade" placeholder="0" />
      <p Style="color:red" v-show="mensagem">
        A quantidade tem que ser maior que 0
      </p>
      <input type="submit" value="Enviar" />
    </div>
  </form>
</template>

<script>
export default {
  name: "HelloWorld",
  emits: ["conteudo"],
  data() {
    return {
      produto: "",
      quantidade: "",
      conteudo: [],
      mensagem: false,
    };
  },
  methods: {
    previewFiles() {
      if (
        this.produto.trim() === "" ||
        this.quantidade === "" ||
        this.quantidade <= 0
      ) {
        this.mensagem = true;
        this.produto = "";
        this.quantidade = "";
      } else {
        this.mensagem = false;
        this.conteudo.push({
          produto: this.produto,
          quantidade: this.quantidade,
        });
        this.$emit("conteudo", this.conteudo);
        this.produto = "";
        this.quantidade = "";
      }
    },
  },
};
</script>

<style scoped>
.fundo {
  background-color: #ccc;
  width: 520px;
  padding: 5px 10px;
  box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
}
.container {
  width: 90%;
  display: flex;
  flex-direction: column;
  margin: 10px auto;
}
h3 {
  padding: 10px 0;
}
input {
  padding: 10px;
  border-radius: 7px;
  border: none;
  margin: 10px 0;
  outline-color: blue;
}
input[type="submit"] {
  padding: 10px;
  border: none;
  border-radius: 10px;
  box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
  background-color: blue;
  font-weight: 500;
  color: #fff;
}
input[type="submit"]:hover {
  background-color: rgb(1, 1, 145);
  transition: 1s;
}
input[type="file"] {
  padding: 10px;
  border: none;
  border-radius: 10px;
  background-color: white;
  font-weight: 500;
  color: rgb(105, 105, 105);
}
@media screen and (max-width: 1086px) {
  .fundo {
    width: 95%;
    margin-top: 20px;
  }
}
</style>
