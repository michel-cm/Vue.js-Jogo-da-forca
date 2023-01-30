<template>
  <div class="jogo">
    <Forca :erros="erros" />
  </div>
</template>

<script>
import Forca from "./ForcaView.vue";

export default {
  name: "JogoView",
  data() {
    return {};
  },
  methods: {},
  props: {
    erros: Number,
  },
  components: {
    Forca,
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
