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
.contenido {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  aling-items: center;
}
</style>
