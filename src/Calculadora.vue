<template>
  <div class="calculadora">
    <input class="entrada" type="number" v-model="x"/>
    <div>
      <input type="radio" id="sum" value="sum" v-model="operador"/>
      <label for="sum">sum</label>
      <input type="radio" id="res" value="res" v-model="operador"/>
      <label for="res">res</label>
      <input type="radio" id="mul" value="mul" v-model="operador"/>
      <label for="mul">mul</label>
      <input type="radio" id="div" value="div" v-model="operador"/>
      <label for="div">div</label>
    </div>
    <input class="entrada" type="number" v-model="y"/>
    <button class="btn-calcular" @click="calcular">=</button>
    <input class="entrada" type="number" v-model="z"/>
    <div class="buttons">
      <button v-for="num in nums">{{num}}</button>
    </div>
  </div>
</template>
<script>
export default {
  name: "calculadora",
  data() {
    return {
      x: 0,
      y: 0,
      z: 0,
      operador: 'sum',
      nums: [1, 2, 3, 4, 5, 6, 7, 8, 9, 0],
    }
  },
  methods: {
    calcular() {
      switch (this.operador) {
        case 'sum':
          this.z = parseInt(this.x) + parseInt(this.y);
          break;
        case 'res':
          this.z = parseInt(this.x) - parseInt(this.y);
          break;
        case 'mul':
          this.z = parseInt(this.x) * parseInt(this.y);
          break;
        case 'div':
          this.z = parseInt(this.x) / parseInt(this.y);
          break;
      }
    }
  }
}
</script>
<style lang="scss" scoped>
.calculadora {
  width: 30%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  aling-items: center;

  .entrada {
    padding: .5em;
    margin: .2em;
    border: 1px solid blue;
  }
  .btn-calcular {
    padding: .5em;
    margin: .2em;
  }
  .buttons {
    display: flex;
    justify-content: space-between;
    button {
      padding: 1em 0;
      width: 30%;
      border: 1px solid orange;
      border-radius: 0;
    }
  }
}
</style>