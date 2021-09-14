<script setup lang="ts">
import { ref, computed } from "vue";

const s1 = ref('')
const s2 = ref('')

const n1 = computed(() => parseInt(s1.value))
const n2 = computed(() => parseInt(s2.value))

const n1malo = computed(() => Number.isNaN(n1.value))
const n2malo = computed(() => Number.isNaN(n2.value))

const op = ref('sum')

const resultado = ref(0)

function calcular() {
    if (op.value == 'sum')
        resultado.value = n1.value + n2.value
    if (op.value == 'res')
        resultado.value = n1.value - n2.value
    if (op.value == 'mul')
        resultado.value = n1.value * n2.value
    if (op.value == 'div')
        resultado.value = n1.value / n2.value
}
</script>

<template>
    <div class="root">
        <div class="calc">
            <input v-model="s1" :class="{malo: n1malo}" type="text" />
            <select v-model="op">
                <option value="sum">+</option>
                <option value="res">-</option>
                <option value="mul">×</option>
                <option value="div">÷</option>
            </select>
            <input v-model="s2" :class="{malo: n2malo}" type="text" />
        </div>
        <button @click="calcular" :disabled="n1malo || n2malo">Calcular</button>
        <p class="hola">Resultado: {{ resultado }}</p>
    </div>
</template>

<style scoped>
.root {
    font-family: "Poppins", sans-serif;
    flex-direction: column;
    align-items: center;
}
.root,
.calc {
    display: flex;
    gap: 8px;
}
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
}
input[type="number"] {
    -moz-appearance: textfield;
}
input,
select {
    appearance: none;
    text-align: center;
    background-color: white;
    border: none;
    font: inherit;
    outline: none;
    padding: 8px;
    width: 64px;

    border: 2px solid midnightblue;
    box-shadow: 4px 4px 0 lightcoral;
}
input.malo {
    border-color: red;
}

button {
    appearance: none;
    border: none;
    font: inherit;
    outline: none;
    background-color: midnightblue;
    color: white;
    padding: 8px 16px;
    border: 2px solid white;
    box-shadow: 4px 4px 0 lightcoral;
    transition: translate .2s ease, box-shadow .2s ease;
}
button:hover {
    translate: -1px -1px;
    box-shadow: 6px 6px 0 lightcoral;
}
button:active {
    translate: 2px 2px;
    box-shadow: 0px 0px 0 lightcoral;
}
button:disabled {
    opacity: .5;
}
.hola {
    font-size: 56px;
    font-weight: 300;
    text-align: center;
}
</style>