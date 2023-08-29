<script>
  export default {
  data() {
    return {
      num1: '',
      num2: '',
      operador: '',
      resultado: 0,
    };
  },
  methods: {
    calcular() {
      switch (this.operador) {
        case "+":
          this.resultado = parseFloat(this.num1) + parseFloat(this.num2);
          break;
        case "-":
          this.resultado = parseFloat(this.num1) - parseFloat(this.num2);
          break;
        case "*":
          this.resultado = parseFloat(this.num1) * parseFloat(this.num2);
          break;
        case "/":
          this.resultado = parseFloat(this.num1) / parseFloat(this.num2);
          break;
      }
    },
  },
};
</script>

<template>
   <div class="calculadora">
    <h2>Calculadora Aritmética</h2>
    <input v-model="num1" @input="calcular" />
    <select v-model="operador" @change="calcular">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <input v-model="num2" @input="calcular" />
    <p>Resultado: {{ resultado }} </p>
  </div>
</template>
  
<style scoped>
.calculadora {
  max-width: 300px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  background-color: burlywood;
}

input,
select {
  margin: 5px;
  padding: 5px;
  width: 100%;
}
</style>
