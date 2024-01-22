<script setup>
import { Calculadora } from './components/Calculadora.vue'
</script>

<template>
    <div class="body">
        <div class="container">
            <header>
                <h1>Calculadora com VueJS</h1>
            </header>
            <Calculadora />
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
</style>
