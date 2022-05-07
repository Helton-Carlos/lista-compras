<template>
  <div>
    <table>
      <tr>
        <td class="base">Produto</td>
        <td class="base">Quantidade</td>
      </tr>
      <tr v-for="produtos in conteudoObj" :key="produtos">
        <td class="gray">
          {{ produtos.produto }}
        </td>
        <td class="gray">
          {{ produtos.quantidade }}
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  props: ["conteudoObj"],
};
</script>

<style>
.base {
  background-color: blue;
  color: #fff;
  padding: 5px 50px;
}
.gray {
  background-color: rgb(206, 206, 206);
  color: #000000;
  font-weight: 500;
  padding: 5px 50px;
}
td {
  text-align: center;
}
.flex-coluna {
  display: flex;
  flex-direction: column;
}
</style>