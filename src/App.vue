<script setup>
import { reactive, watch } from 'vue'

const estado = reactive({
    primeiroNumero: 0,
    segundoNumero: 0,
    resultado: 0,
    operacao: ''
})

const calcularResultado = () => {

    switch (estado.operacao) {
        case "soma":
            estado.resultado = estado.primeiroNumero + estado.segundoNumero
            break;
        case 'subtracao':
            estado.resultado = estado.primeiroNumero - estado.segundoNumero
            break;
        case 'multiplicacao':
            estado.resultado = estado.primeiroNumero * estado.segundoNumero
            break;
        case 'divisao':
            estado.resultado = estado.primeiroNumero / estado.segundoNumero
            break;
        default:
            estado.resultado = 0
            break;
    }
    console.log(primeiroNumero)
    console.log(segundoNumero)
    console.log(estado.resultado)
    console.log(estado.operacao)
}



</script>

<template>
    <div class="body">
        <div class="container">
            <header>
                <h1>Calculadora com VueJS</h1>
            </header>

            <form>
                <div class="calc mt-4">
                    <div class="form-group me-3">
                        <label for="primeiroNumero">Digite o primeiro número</label>
                        <input @input="calcularResultado" v-model="estado.primeiroNumero" type="number"
                            class="form-control" placeholder="Primeiro Número">
                    </div>
                    <div class="form-group">
                        <label for="segundoNumero">Digite o segundo número</label>
                        <input @input="calcularResultado" v-model="estado.segundoNumero" type="number"
                            class="form-control" placeholder="Segundo Número">
                    </div>
                </div>
                <div class="form-group operacao">
                    <label for="escolhaDaOperacao"><strong>Escolha a operação</strong></label>
                    <select @change="calcularResultado" v-model="estado.operacao" name="escolhaDaOperacao" id="escolhaDaOperacao">
                        <option value="soma">Soma</option>
                        <option value="subtracao">Subtração</option>
                        <option value="multiplicacao">Multiplicação</option>
                        <option value="divisao">Divisão</option>
                    </select>
                </div>
                <div class="resultado mt-5">
                    <h3>O resultado da operação é <span> <strong>{{ estado.resultado }}</strong> </span></h3>
                </div>
            </form>
        </div>
    </div>
</template>

<style scoped>
.body {
    background-color: rgb(247, 245, 245);
}

header {
    color: rgb(32, 32, 182);
}

.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: rgb(221, 212, 212);
    min-height: 100vh;
}

.calculator-form {
    width: 100%;
}

.calc,
.operacao {
    display: flex;
    justify-content: center;
    padding: 20px;
}

.resultado {
    text-align: center;
}

span {
    color: rgb(189, 31, 31);
}
</style>
