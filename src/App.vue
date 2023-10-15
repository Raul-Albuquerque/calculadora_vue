<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';

  const estado = reactive({
    numero1: 0,
    numero2: 0,
    operacao: '',
    resultado: 0
  })

  const somar = () => {
    return estado.resultado = estado.numero1 + estado.numero2;
  }

  const subtrair = () => {
    return estado.resultado = estado.numero1 - estado.numero2;
  }

  const multiplicar = () => {
    return estado.resultado = estado.numero1 * estado.numero2;
  }

  const dividir = () => {
    return estado.resultado = estado.numero1 / estado.numero2;
  }

  const realizarOperacao = () => {
    const { operacao } = estado;

    switch(operacao) {
      case '+':
        return somar();
      case '-':
        return subtrair();
      case '/':
        return dividir();
      case '*':
        return multiplicar();
    }
  }

</script>

<template>
  <div class="container">
    <Cabecalho/>
    <Formulario 
      :get-number1="evento => estado.numero1 = Number(evento.target.value)" 
      :get-number2="evento => estado.numero2 = Number(evento.target.value)"
      :get-operation="evento => estado.operacao = evento.target.value"
      :realizar-operacao="realizarOperacao()" 
      :get-resultado="estado.resultado"/>
  </div>  
</template>
