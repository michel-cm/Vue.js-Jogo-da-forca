<template>
  <div class="formulario">
    <div class="formulario-title">{{ title }}</div>
    <input type="text" class="formulario-input" />
    <button>{{ button }}</button>
  </div>
</template>

<script>
export default {
  name: "FormularioView",
  props: {
    title: String,
    button: String,
  },
};
</script>

<style scoped>
.formulario {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  margin-top: 20px;
}

.formulario-input {
  padding: 10px 5px;
  border: 0;
  border-radius: 5px;
  margin: 10px 0;
  text-align: center;
  color: var(--color-text-dark);
  font-size: 16px;
}
</style>
