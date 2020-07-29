<template>
  <div>
    <Rotulo nome="Nome">
      <input @input="alterarNome" type="text" :value="value.nome" />
    </Rotulo>
    <Rotulo nome="Sobrenome">
      <input @input="alterarSobrenome" type="text" :value="value.sobrenome" />
    </Rotulo>
  </div>
</template>

<script>
import Rotulo from "./Rotulo.vue";
export default {
  props: {
    value: {
      type: Object,
      required: true,
    },
  },
  components: { Rotulo },
  methods: {
    alterarNome(event) {
      this.$emit("input", {
        nome: event.target.value,
        sobrenome: this.value.sobrenome,
      });
    },
    alterarSobrenome(event) {
      this.$emit("input", {
        nome: this.value.nome,
        sobrenome: event.target.value,
      });
    },
  },
};
</script>

<style scoped>
</style>
