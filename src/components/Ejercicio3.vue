<script setup lang="ts">
import { ref, computed } from "vue";
import Base from "./util/Base.vue";
import Button from "./util/Button.vue";

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
    <Base>
        <h2>Calculadora +</h2>
        <div class="calc">
            <input v-model="s1" :aria-invalid="n1malo" type="text" />
            <select v-model="op">
                <option value="sum">+</option>
                <option value="res">-</option>
                <option value="mul">×</option>
                <option value="div">÷</option>
            </select>
            <input v-model="s2" :aria-invalid="n2malo" type="text" />
        </div>
        <Button @click="calcular" :disabled="n1malo || n2malo">Calcular</Button>
        <p class="big">Resultado: {{ resultado }}</p>
    </Base>
</template>

<style scoped>
.calc {
    display: flex;
    gap: 8px;
}
</style>