<style>
@import './styles.css';
</style>

<template>
  <div id="app">
    <label class="label1" for="numero1">Número 1:</label>
    <input v-model="numero1" type="number" @input="calcularResultado" />

    <label class="label" for="numero2">Número 2:</label>
    <input v-model="numero2" type="number" @input="calcularResultado" />

  

    <label class="respotlabe" for="operacao">Operação:</label>
    <select v-model="operacao" @change="calcularResultado">
      <option value="soma">Soma</option>
      <option value="subtracao">Subtração</option>
      <option value="divisao">Divisão</option>
      <option value="multiplicacao">Multiplicação</option>
      <!-- Adicione mais operações conforme necessário -->
    </select>

    <p>Resultado: {{ resultado }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: 'soma',
      resultado: 0,
    };
  },
  methods: {
    calcularResultado() {
      switch (this.operacao) {
        case 'soma':
          this.resultado = this.numero1 + this.numero2;
          break;
        case 'subtracao':
          this.resultado = this.numero1 - this.numero2;
          break;
        case 'divisao':
          this.resultado = this.numero1 / this.numero2
          break;
          case 'multiplicacao':
            if(this.numero2 != 0){
              this.resultado = this.numero1 * this.numero2;
            }else{
              alert("Não é possível dividir por zero");
            }
            
          break;
        default:
          this.resultado = 0;
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
