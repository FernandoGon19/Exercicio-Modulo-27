<script setup>
import { reactive } from 'vue';

    const numero = reactive({
        num1: '',
        num2: '',
        calculo: '',
        resultado: ''
    })

    

    function adicionarNumero1(evento) {
        numero.num1 += evento.target.value
    }

    function adicionarNumero2(evento) {
        numero.num2 += evento.target.value
    }

    function aritmetica(evento){
        numero.calculo = evento.target.value
        console.log(numero.calculo)
    }

    function calcular(num1, num2, calculo) {
        if (calculo == '-') {
            return num1 - num2
        } else if(calculo == '+') {
            return Number(num1) + Number(num2)
        } else if(calculo == '/') {
            return num1 / num2
        } else if(calculo == '*') {
            return num1 * num2
        }
           
        
    }

    function apagar() {
        numero.num1 = ' '
        numero.num2 = ' '
    }

</script>

<template>

    <h1>{{ numero.num1 }} {{ numero.calculo }} {{ numero.num2 }} = {{ calcular(numero.num1, numero.num2, numero.calculo) }}</h1>
    
    <section>
        <div>
            <button @click="adicionarNumero1" value="1">1</button>
            <button @click="adicionarNumero1" value="2">2</button>
            <button @click="adicionarNumero1" value="3">3</button>
            <button @click="adicionarNumero1" value="4">4</button>
            <button @click="adicionarNumero1" value="5">5</button>
            <button @click="adicionarNumero1" value="6">6</button>
            <button @click="adicionarNumero1" value="7">7</button>
            <button @click="adicionarNumero1" value="8">8</button>
            <button @click="adicionarNumero1" value="9">9</button>
            <button @click="adicionarNumero1" value="0">0</button>
        </div>

        <div>
            <button @click="adicionarNumero2" value="1">1</button>
            <button @click="adicionarNumero2" value="2">2</button>
            <button @click="adicionarNumero2" value="3">3</button>
            <button @click="adicionarNumero2" value="4">4</button>
            <button @click="adicionarNumero2" value="5">5</button>
            <button @click="adicionarNumero2" value="6">6</button>
            <button @click="adicionarNumero2" value="7">7</button>
            <button @click="adicionarNumero2" value="8">8</button>
            <button @click="adicionarNumero2" value="9">9</button>
            <button @click="adicionarNumero2" value="0">0</button>
        </div>
    
        <select @change="aritmetica">
        <option value=" ">Selecione</option>
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="/">/</option>
        <option value="*">*</option>
    </select>
    <button @click="apagar">Apagar</button>

    
    </section>
    

 

</template>

<style>
</style>