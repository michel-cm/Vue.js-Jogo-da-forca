<template>
  <div class="teclado">
    <button
      class="teclado-botao"
      v-for="(letra, key) in 'abcdefghijklmnopqrstuvwxyz'"
      :key="key"
      :disabled="verificarLetra(letra)"
      @click="jogar(letra)"
    >
      {{ letra }}
    </button>
  </div>
</template>

<script>
export default {
  name: "TecladoView",
  data() {
    return {};
  },
  props: {
    letras: Array,
    verificarLetra: Function,
    jogar: Function,
  },
};
</script>

<style scoped>
.teclado {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  margin-top: 20px;
}

.teclado-botao {
  margin: 5px;
  text-transform: uppercase;
}
</style>
