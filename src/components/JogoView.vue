<template>
  <div class="jogo">
    <ForcaView :erros="erros" />

    <PalavraView
      :palavra="palavra"
      :dica="dica"
      :verificarLetra="verificarLetra"
      :etapa="etapa"
    />

    <TecladoView
      :letras="letras"
      :verificarLetra="verificarLetra"
      :jogar="jogar"
      v-if="etapa === 'jogo'"
    />

    <FinalView
      v-if="etapa != 'jogo'"
      :etapa="etapa"
      :texto="etapa === 'ganhador' ? 'Parabens :)' : 'Perdeu :C'"
      :jogarNovamente="jogarNovamente"
    />
  </div>
</template>

<script>
import ForcaView from "./ForcaView.vue";
import PalavraView from "./PalavraView.vue";
import TecladoView from "./TecladoView.vue";
import FinalView from "./FinalView.vue";

export default {
  name: "JogoView",
  data() {
    return {};
  },
  methods: {},
  props: {
    erros: Number,
    palavra: String,
    dica: String,
    verificarLetra: Function,
    etapa: String,
    letras: Array,
    jogar: Function,
    jogarNovamente: Function,
  },
  components: {
    ForcaView,
    PalavraView,
    TecladoView,
    FinalView,
  },
};
</script>

<style scoped>
.jogo {
  width: 100%;
  display: flex;
  flex-direction: column;
  text-align: center;
}
</style>
