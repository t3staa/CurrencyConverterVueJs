<template> 
  <div id="app">
    <h1 class="titulo">Conversão de Moedas</h1>
    <ConversorComponent moedaA="USD" moedaB="BRL"/>
  </div>
  <footer>
    <p>Autor: Leonardo Testa | Data: 30/07/2024</p>
    <p><a href="mailto:testa.leo@outlook.com">testa.leo@outlook.com</a></p>
  </footer>
</template>

<script> 
import ConversorComponent from "./components/Conversor.vue";

export default {
  name: 'App',
  components: {
    ConversorComponent
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
  margin: 40px;
  padding: 2px;
}
footer {
  padding: 5px;
  background-color:#373737;
  color: white;
  box-shadow: 0 .5rem 1.5rem rgba(0,0,0,.1);
  border-radius: .5rem;
  border: .1rem solid rgba(0,0,0,.1);
  margin-right: 75px;
  margin-left: 75px;
}

@media(max-width: 449px){
  #app {
    margin: 20px;
    margin-top: 20px;
    padding: 2px;
    display: grid;
  }

  footer {
    padding: 2px;
    margin-right: 27px;
    margin-left: 27px;
  }
}

@media (min-width: 450px) and (max-width: 830px){
  #app {
    margin: auto;
    margin-top: 20px;
    padding: 2px;
    display: grid;
  }

  footer {
    padding: 2px;
    margin-right: 9px;
    margin-left: 9px;
  }
}
</style>
