<template>
  <div class="calculadora">
    <input type="text" class="input"/>
    <div class="buttons">
      <button>7</button>
      <button>8</button>
      <button>9</button>
      <button>+</button>

      <button>4</button>
      <button>5</button>
      <button>6</button>
      <button>-</button>

      <button>1</button>
      <button>2</button>
      <button>3</button>
      <button>*</button>

      <button>C</button>
      <button>0</button>
      <button>=</button>
      <button>/</button>
    </div>
  </div>
</template>
<script>
export default {
  name: "calculadora",
}
</script>
<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css?family=Dosis&display=swap');
$orange: orange;
.calculadora {
  width: 30%;
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
    }
  }
}
</style>