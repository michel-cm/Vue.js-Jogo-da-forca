<template>
  <div id="app">
    <h1>Jogo da Forca WDEV</h1>

    <section class="inicio" v-if="tela === 'inicio'">
      <FormularioView
        v-if="etapa === 'palavra'"
        title="Defina a palavra"
        button="Próximo"
        :action="setPalavra"
      />
      <FormularioView
        v-if="etapa === 'dica'"
        title="Defina a dica"
        button="Iniciar jogo :)"
        :action="setDica"
      />
    </section>

    <section class="jogo" v-if="tela === 'jogo'">
      <JogoView :erros="erros" />
    </section>
  </div>
</template>

<script>
import "./css/global.css";
import FormularioView from "@/components/FormularioView.vue";
import JogoView from "@/components/JogoView.vue";

export default {
  name: "App",
  data() {
    return {
      tela: "inicio",
      etapa: "palavra",
      palavra: "",
      dica: "",
      erros: 0,
    };
  },
  methods: {
    setPalavra(palavra) {
      this.palavra = palavra;
      this.etapa = "dica";
    },
    setDica(dica) {
      this.dica = dica;
      this.tela = "jogo";
      this.etapa = "jogo";
    },
  },
  components: {
    FormularioView,
    JogoView,
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
