<script>
export default {
  data() {
    return {
      valor1: 0,
      valor2: 0,
      operation: 'soma',
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case 'soma':
          return this.valor1 + this.valor2;
        case 'subtrai':
          return this.valor1 - this.valor2;
        case 'multiplica':
          return this.valor1 * this.valor2;
        case 'divide':
          return this.valor2 !== 0 ? this.valor1 / this.valor2 : 'Não é possível dividir por zero';
        default:
          return 0;
      }
    },
  },
};
</script>

<template>
  <div id="app" class="calculadora">
    <h1>Calculadora Aritmética</h1>

    <div>
      <input type="number" v-model="valor1" placeholder="Número 1" />
      <input type="number" v-model="valor2" placeholder="Número 2" />
    </div>

    <div>
      <select v-model="operation">
        <option value="soma">soma</option>
        <option value="subtrai">subtração</option>
        <option value="multiplica">multiplicação</option>
        <option value="divide">divisão</option>
      </select>
    </div>

    <div>
      <h2>Resultado: {{ result }}</h2>
    </div>
  </div>
</template>

<style scoped>
.calculadora {
  max-width: 300px;
  margin: 0 auto;
  text-align: center;
}

input {
  margin: 5px;
}

select {
  margin: 5px;
}
</style>
