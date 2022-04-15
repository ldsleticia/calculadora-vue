<template>
  <HelloWorld/>
  <HelloWorld/>
  <ComponenteX/>
</template>

<script>
import HelloWorld from '../components/HelloWorld.vue'
import ComponenteX from '../components/ComponenteX.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    ComponenteX
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
