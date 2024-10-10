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
    <div class="calculadora container mt-5">
        <h1 class="text-center mb-4">Calculadora Aritmética</h1>

        <div class="row mb-3">
            <div class="col">
                <input type="number" v-model="valor1" placeholder="Número 1" class="form-control" />
            </div>
            <div class="col">
                <input type="number" v-model="valor2" placeholder="Número 2" class="form-control" />
            </div>
        </div>

        <div class="row mb-3">
            <div class="col">
                <select v-model="operation" class="form-select">
                    <option value="soma">Soma</option>
                    <option value="subtrai">Subtração</option>
                    <option value="multiplica">Multiplicação</option>
                    <option value="divide">Divisão</option>
                </select>
            </div>
        </div>

        <div class="row">
            <div class="col">
                <h2 class="text-center">Resultado: {{ result }}</h2>
            </div>
        </div>
    </div>
</template>

<style scoped>
.calculadora {
    max-width: 400px;
}
</style>