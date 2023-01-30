<template>
  <div class="jogo">
    <ForcaView :erros="erros" />

    <PalavraView
      :palavra="palavra"
      :dica="dica"
      :verificarLetra="verificarLetra"
      :etapa="etapa"
    />
  </div>
</template>

<script>
import ForcaView from "./ForcaView.vue";
import PalavraView from "./PalavraView.vue";

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
  },
  components: {
    ForcaView,
    PalavraView,
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
