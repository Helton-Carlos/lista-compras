<template>
  <form class="fundo" @submit.prevent="previewFiles()">
    <div class="container">
      <h3>Lista de compras</h3>
      <input type="text" v-model="produto" placeholder="Nome do produto" />
      <input type="number" v-model="quantidade" placeholder="0" />
      <input type="file" />
      <input type="submit" value="Enviar" />
    </div>
  </form>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      produto: "",
      quantidade: "",
    };
  },
  methods: {
    previewFiles() {
      console.log(this.produto);
      console.log(this.quantidade);
    },
  },
};
</script>

<style scoped>
.fundo {
  background-color: #ccc;
  width: 320px;
  margin: 20px auto;
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
}
input[type="button"] {
  padding: 10px;
  border: none;
  border-radius: 10px;
  box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
  background-color: blue;
  font-weight: 500;
  color: #fff;
}
input[type="button"]:hover {
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
</style>
