<template>
  <div id="app">
    <h1>Jogo da Forca WDEV</h1>

    <section class="inicio" v-if="tela === 'inicio'">Inicio</section>

    <section class="jogo" v-if="tela === 'jogo'">jogo</section>
  </div>
</template>

<script>
import "./css/global.css";

export default {
  name: "App",
  data() {
    return {
      tela: "inicio",
    };
  },
  components: {},
};
</script>

<style>
#app {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
