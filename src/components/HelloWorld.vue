<template>
  <h1>Inc {{ contador }}</h1>
  <h1>Dec {{ contador }}</h1>
  <button @click="incrementar">Eu somo um</button>
  <button @click="decrementar">Eu subtraio</button>
</template>

<script>
export default {
  data: function () {
    return {
      contador: 0,
    };
  },
  methods: {
    incrementar() {
      this.contador++;
    },
    decrementar() {
      this.contador--;
    },
  },
};
</script>