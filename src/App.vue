<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: '+',
      resultado: 0,
    };
  },
  methods: {
    calcularResultado() {
      switch (this.operacao) {
        case '+':
          this.resultado = this.numero1 + this.numero2;
          break;
        case '-':
          this.resultado = this.numero1 - this.numero2;
          break;
        case '*':
          this.resultado = this.numero1 * this.numero2;
          break;
        case '/':
          this.resultado = this.numero1 / this.numero2;
          break;
        default:
          this.resultado = 0;
      }
    },
  },
};
</script>

<template>
  <div id="app" class="container mt-5">
    <h1>Calculadora Aritmética</h1>

    <div class="row">
      <div class="col-md-4">
        <label for="numero1">Número 1:</label>
        <input v-model="numero1" @input="calcularResultado" type="number" id="numero1" class="form-control" />
      </div>

      <div class="col-md-4">
        <label for="operacao">Operação:</label>
        <select v-model="operacao" @change="calcularResultado" id="operacao" class="form-control">
          <option value="+">+</option>
          <option value="-">-</option>
          <option value="*">*</option>
          <option value="/">/</option>
        </select>
      </div>

      <div class="col-md-4">
        <label for="numero2">Número 2:</label>
        <input v-model="numero2" @input="calcularResultado" type="number" id="numero2" class="form-control" />
      </div>
    </div>

    <div class="mt-3">
      <strong>Resultado: {{ resultado }}</strong>
    </div>
  </div>
</template>

<style>
    .container{
      width: 90vh;
      height: 60vh;
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      justify-items: center;
      align-items: center;
      grid-template-areas: "titulo opcoes" "resultado opcoes";
      background: #61677A;
      border-radius: 10px;
    }

    .row, label, input, option, select{
      font-size: 1.4rem;
      font-weight: bold;
      padding: 0.5em;
      margin: 0.5em 0;
    }

    .mt-3{
      font-size: 1.4rem;
    }
</style>
