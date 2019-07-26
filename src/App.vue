<template>
  <div id="app">
    <div class="contenido">
      <h1>Calculadora</h1>
      <calculadora/>
    </div>    
  </div>
</template>

<script>
import Calculadora from './Calculadora';
export default {
  name: 'app',
  components: {
    'calculadora': Calculadora
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Quicksand&display=swap');
.contenido {
  font-family: 'Quicksand', sans-serif;
  font-size: 1.5em;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
