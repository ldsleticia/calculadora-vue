<template>
  <CalculadoraView/>
  <UIButton/>
</template>

<script>
import CalculadoraView from './components/CalculadoraView.vue'
import UIButton from './components/UIButton.vue'

export default {
  name: 'App',
  components: {
    CalculadoraView,
    UIButton,
  }
}
</script>
