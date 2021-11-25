<script setup lang="ts">
import { ref, onMounted } from "vue";
import Base from "./util/Base.vue";
import Button from "./util/Button.vue";

const n1 = ref(0)
const n2 = ref(0)

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
    <Base>
        <h2>Calculadora</h2>
        <div class="calc">
            <input v-model.number="n1" type="number" />
            <select v-model="op">
                <option value="sum">+</option>
                <option value="res">-</option>
                <option value="mul">×</option>
                <option value="div">÷</option>
            </select>
            <input v-model.number="n2" type="number" />
        </div>
        <Button @click="calcular">Calcular</Button>
        <p class="big">Resultado: {{ resultado }}</p>
    </Base>
</template>

<style scoped>
.calc {
    display: flex;
    gap: 8px;
}
</style>