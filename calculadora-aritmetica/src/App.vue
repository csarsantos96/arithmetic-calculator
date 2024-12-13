<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div>
      <label for="num1">Número 1:</label>
      <input id="num1" type="number" v-model.number="num1" />
    </div>
    <div>
      <label for="num2">Número 2:</label>
      <input id="num2" type="number" v-model.number="num2" />
    </div>
    <div>
      <label for="operation">Operação:</label>
      <select id="operation" v-model="operation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">×</option>
        <option value="divide">÷</option>
      </select>
    </div>
    <div>
      <h2>Resultado: {{ result }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: "add",
    };
  },
  computed: {
    result() {
      const { num1, num2, operation } = this;
      if (operation === "add") return num1 + num2;
      if (operation === "subtract") return num1 - num2;
      if (operation === "multiply") return num1 * num2;
      if (operation === "divide") return num2 !== 0 ? num1 / num2 : "Erro: Divisão por zero";
      return 0;
    },
  },
};
</script>

<style>
#app {
  text-align: center;
  margin-top: 50px;
  font-family: Arial, sans-serif;
}

label {
  display: block;
  margin: 10px 0 5px;
}

input,
select {
  padding: 5px;
  margin: 5px 0 15px;
  font-size: 16px;
}

h2 {
  margin-top: 20px;
}

h2.error {
  color: red;
}
</style>
