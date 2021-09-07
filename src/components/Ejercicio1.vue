<script setup lang="ts">
import { ref } from "vue";

const nombre = ref('')
</script>

<template>
    <div class="root">
        <input autofocus v-model="nombre" type="text" />
        <p class="hola">Hola, {{ nombre || '...' }}</p>
    </div>
</template>

<style scoped>
.root {
    font-family: "Poppins", sans-serif;
    display: flex;
    height: 100%;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}
input {
    background-color: white;
    border: none;
    font: inherit;
    outline: none;
    padding: 8px;
    border: 2px solid black;
    box-shadow: 4px 4px 0 lightcoral;
    margin-bottom: 8px;
}
.hola {
    font-size: 56px;
    font-weight: 300;
    text-align: center;
}
</style>