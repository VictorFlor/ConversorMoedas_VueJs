<template>
  <h1>Conversor de Moedas</h1>
  <div class="linha">
    <ConversorMoeda moedaA="USD" moedaB="BRL" />
    <ConversorMoeda moedaA="EUR" moedaB="BRL" />
    <ConversorMoeda moedaA="JPY" moedaB="BRL" />
  </div>
  <div class="linha">
    <ConversorMoeda moedaA="BRL" moedaB="USD" />
    <ConversorMoeda moedaA="EUR" moedaB="USD" />
    <ConversorMoeda moedaA="JPY" moedaB="USD" />
  </div>
</template>

<script>
import ConversorMoeda from './components/ConversorMoeda.vue'

export default {
  name: 'App',
  components: {
    ConversorMoeda
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}

.linha{
  display: flex;
  justify-content: center;
  margin-top: 100px;
}

</style>
