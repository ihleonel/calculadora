<template>
  <div class="calculadora">
    <div class="logs">
      <span v-for="log in logs">{{log}}</span>
    </div>
    <input type="string" class="input" v-model="value" @keyup.enter="getResult()"/>
    <div class="buttons">
      <button @click="clear()">C</button>
      <button @click="del()">del</button>
      <button @click="addExpresion('%')">%</button>
      <button @click="addExpresion('/')">/</button>

      <button @click="addExpresion('7')">7</button>
      <button @click="addExpresion('8')">8</button>
      <button @click="addExpresion('9')">9</button>
      <button @click="addExpresion('*')">*</button>

      <button @click="addExpresion('4')">4</button>
      <button @click="addExpresion('5')">5</button>
      <button @click="addExpresion('6')">6</button>
      <button @click="addExpresion('-')">-</button>

      <button @click="addExpresion('1')">1</button>
      <button @click="addExpresion('2')">2</button>
      <button @click="addExpresion('3')">3</button>
      <button @click="addExpresion('+')">+</button>

      <button @click="addExpresion('0')" class="wide">0</button>
      <button @click="addExpresion('.')">.</button>
      <button @click="getResult()">=</button>
    </div>
  </div>
</template>
<script>
export default {
  name: "calculadora",
  data() {
    return {
      value: 0,
      logs: []
    }
  },
  methods: {
    addExpresion(e) {
      if (Number.isInteger(this.value)) {
        this.value = '';
      }
      this.value += e;
    },
    getResult() {
      let log = this.value;
      this.value = eval(this.value);
      this.logs.push(log + ' = ' + this.value);
    },
    clear() {
      this.value = 0;
    },
    del() {
      this.value = this.value.slice(0, -1);
    }
  }
}
</script>
<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css?family=Dosis&display=swap');
$orange: orange;
.calculadora {
  width: 30%;
  .logs {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    justify-content: flex-end;
    background-color: #222;
    color: white;
  }
  .input {
    outline: 0;
    font-family: 'Dosis';
    box-sizing: border-box;
    padding: 10px;
    width: 100%;
    border: 0;
    font-size: 2em;
    text-align: right;
    background-color: #222;
    color: white;
  }
  .buttons {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    align-content: stretch;
    button {
      background-color: $orange;
      font-family: 'Dosis';
      padding: .3em;
      width: 25%;
      border: none;
      margin: 0;
      font-size: 2em;
      transition: all 0.2s ease-in;

      &:hover{
        background-color: darken($orange, 5%);
      }
      &:active {
        background-color: #222;
        color: white;
        transition: all 0s ease;
      }
      &:focus {
        outline: 0;
      }

      &.wide {
        width: 50%;
      }
    }
  }
}
</style>