<script setup>

  import { ref, computed } from "vue";


// Criando as variáveis

  const num1 = ref('');
  const num2 = ref('');
  const operacao = ref('escolha');


// Criando a função que calcula o resultado

  const resultado = computed(() => {
    switch (operacao.value) {
      case "+":
        return num1.value + num2.value;
      case "-":
        return num1.value - num2.value;
      case "*":
        return num1.value * num2.value;
      case "/":
        return num1.value / num2.value
      default:
        return '';
    }
  });

</script>

<template>
  
  <div class="container col-3 mt-5 mb-5 rounded-3 shadow-lg p-3 mb-5 rounded border border-secondary bg-secondary-subtle">
        <header>
            <h1 class="h2 text-center mb-3">Calculadora</h1>
        </header>
        <div>
            <div>
                <label class="form-label" for="num1">Número 1:</label>
                <input class="form-control mb-3 border-secondary-subtle" v-model="num1" type="number" id="num1" placeholder="Digite um número">
            </div>
            <div>
                <label class="form-label" for="num2">Número 2:</label>
                <input class="form-control mb-3 border-secondary-subtle" v-model="num2" type="number" id="num2" placeholder="Digite um número">  
            </div>
        </div>
        <div>
            <label class="form-label" for="operacao">Selecione uma operação:</label>
            <select class="form-select mb-3 border-secondary-subtle" v-model="operacao" id="operacao">
                <option value="escolha" disabled selected>Selecione uma operação</option>
                <option value="+">Soma</option>
                <option value="-">Subtração</option>
                <option value="*">Multiplicação</option>
                <option value="/">Divisão</option>
            </select>
        </div>
        <div>
            <h5>Resultado: {{ resultado }} </h5>
        </div>
  </div>

</template>