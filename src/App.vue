<template> 
  <div id="app">
    <h1>Conversão de Moedas</h1>
    <ConversorComponetUSD_BRL moedaA="USD" moedaB="BRL"/>
  </div>
</template>

<script> 
import ConversorComponetUSD_BRL from "./components/Conversor.vue";

export default {
  name: 'App',
  components: {
    ConversorComponetUSD_BRL
  }
};
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
