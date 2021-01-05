<template>
  <div id="app">
    <h1 class="text-center">Conversor de Moedas</h1>

    <div class="coluna">
      <Legenda />
    </div>

    <div class="linha">
      <Conversor moeda-a="USD" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="USD" />
    </div>

    <div class="linha">
      <Conversor moeda-a="CAD" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="CAD" />
    </div>

    <div class="linha">
      <Conversor moeda-a="EUR" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="EUR" />
    </div>
  </div>
</template>

<script>
import Conversor from "./components/conversor";
import Legenda from "./components/legenda";
export default {
  name: 'App',
  components: {
    Conversor,
    Legenda
  }
}
</script>

<style>
body {
  background-image: url(./assets/image/money-bg.jpg);
}
#app {
  margin: auto;
  max-width: 900px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.linha {
  margin-top: 40px;
  display: flex;
  justify-content: space-around;
}

.text-center {
  text-align: center;
  color: #fff;
  font-weight: 700;
}

@media (max-width: 739px) {
  #app {
    width: 200px;
  }

  .linha {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
  }
}
</style>
