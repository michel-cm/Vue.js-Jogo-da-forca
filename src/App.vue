<template>
  <div id="app">
    <h1>Jogo da Forca WDEV</h1>

    <section class="inicio" v-if="tela === 'inicio'">
      <FormularioView title="Defina a palavra" button="Próximo" />
      <FormularioView title="Defina a dica" button="Iniciar jogo :)" />
    </section>

    <section class="jogo" v-if="tela === 'jogo'">jogo</section>
  </div>
</template>

<script>
import "./css/global.css";
import FormularioView from "@/components/FormularioView.vue";

export default {
  name: "App",
  data() {
    return {
      tela: "inicio",
    };
  },
  components: {
    FormularioView,
  },
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
