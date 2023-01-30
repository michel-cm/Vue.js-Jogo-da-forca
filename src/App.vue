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
      <JogoView
        :erros="erros"
        :palavra="palavra"
        :dica="dica"
        :verificarLetra="verificarLetra"
        :etapa="etapa"
        :letras="letras"
        :jogar="jogar"
      />
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
      letras: [],
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
    verificarLetra(letra) {
      return this.letras.find(
        (item) => item.toLowerCase() === letra.toLowerCase()
      );
    },

    jogar(letra) {
      // add letra jogada
      this.letras.push(letra);

      //validar erro
      this.verificarErros(letra);
    },

    verificarErros(letra) {
      //acerto
      if (this.palavra.toLowerCase().indexOf(letra.toLowerCase()) >= 0) {
        return this.verifcarAcertos();
      }

      //erros
      this.erros++;

      //enforcado
      if (this.erros === 6) {
        this.etapa = "enforcado";
      }
    },

    verificarAcertos() {
      let letrasUnicas = [...new Set(this.palavra.split(""))];
      if (letrasUnicas.length === this.letras.length - this.erros) {
        this.etapa = "ganhador";
      }
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
