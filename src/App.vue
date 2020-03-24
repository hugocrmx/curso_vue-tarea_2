<template>
  <div id="app">
    <CardItem
      name="Java"
      :show-details="true"
      description="Es un lenguaje de programación orientado a objetos que se incorporó al ámbito de la informática en los años noventa. La idea de Java es que pueda realizarse programas con la posibilidad de ejecutarse en cualquier contexto, en cualquier ambiente, siendo así su portabilidad uno de sus principales logros."
      url-image="https://live.mrf.io/statics/i/ps/www.muylinux.com/wp-content/uploads/2020/03/java.png" />
  </div>
</template>

<script>
import CardItem from "@/components/CardItem";
export default {
  name: "App",
  components:{
    CardItem
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  display: flex;
  margin-top: 64px;
  justify-content: center;
}
</style>