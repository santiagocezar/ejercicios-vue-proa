<script setup lang="ts">
import { ref } from "vue";
import Base from "./util/Base.vue";
import Button from "./util/Button.vue";

const lista = ref<string[]>([])
const porAgregar = ref('')

function agregar() {
    lista.value = [porAgregar.value, ...lista.value]
    porAgregar.value = ''
}

</script>

<template>
    <Base>
        <h2>Lista de compras</h2>
        <div class="calc">
            <input v-model="porAgregar" type="text" @keypress.enter="agregar" />
            <Button @click="agregar">+</Button>
        </div>
        <ul v-if="lista.length">
            <li v-for="item in lista">{{ item }}</li>
        </ul>
        <p v-else class="big">Vacío</p>
    </Base>
</template>

<style scoped>
.calc {
    display: flex;
    gap: 8px;
}
input {
    width: unset;
}
</style>