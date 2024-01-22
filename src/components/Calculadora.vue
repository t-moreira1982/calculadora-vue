<script setup>
import { reactive } from 'vue'

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
}
</script>

<template>
    <form>
        <div class="calc mt-4">
            <div class="form-group me-3">
                <label for="primeiroNumero">Digite o primeiro número</label>
                <input @input="calcularResultado" v-model="estado.primeiroNumero" type="number" class="form-control"
                    placeholder="Primeiro Número">
            </div>
            <div class="form-group">
                <label for="segundoNumero">Digite o segundo número</label>
                <input @input="calcularResultado" v-model="estado.segundoNumero" type="number" class="form-control"
                    placeholder="Segundo Número">
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
</template>

<style scoped>
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