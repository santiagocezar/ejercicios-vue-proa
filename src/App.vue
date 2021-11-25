<script setup lang="ts">
import { ref } from "vue";
import Ejercicio1 from "./components/Ejercicio1.vue";
import Ejercicio2 from "./components/Ejercicio2.vue";
import Ejercicio3 from "./components/Ejercicio3.vue";
import Ejercicio4 from "./components/Ejercicio4.vue";
import Ejercicio5 from "./components/Ejercicio5.vue";
import Ejercicio6 from "./components/Ejercicio6.vue";
import Ejercicio7 from "./components/Ejercicio7/Ejercicio.vue";
import Ejercicio8 from "./components/Ejercicio8.vue";

const ej = ref('1')


</script>

<template>
    <div class="center">
        <h1>Recortes de ejercicios</h1>
        <select v-model="ej">
            <option value="1">Ejercicio 1</option>
            <option value="2">Ejercicio 2</option>
            <option value="3">Ejercicio 3</option>
            <option value="4">Ejercicio 4</option>
            <option value="5">Ejercicio 5</option>
            <option value="6">Ejercicio 6</option>
            <option value="7">Ejercicio 7</option>
            <option value="8">Ejercicio 8</option>
        </select>
    </div>
    <div class="ejercicio">
        <Ejercicio1 v-if="ej == '1'" />
        <Ejercicio2 v-if="ej == '2'" />
        <Ejercicio3 v-if="ej == '3'" />
        <Ejercicio4 v-if="ej == '4'" />
        <Ejercicio5 v-if="ej == '5'" />
        <Ejercicio6 v-if="ej == '6'" />
        <Ejercicio7 v-if="ej == '7'" />
        <Ejercicio8 v-if="ej == '8'" />
    </div>
</template>

<style>
* {
    margin: 0;
    padding: 0;
}

html,
body,
#app {
    font-family: "Poppins", sans-serif;
    background-color: lightcoral;
    /*background-image: url("/assets/caprincho.jpg");
    background-size: cover;
    background-position: center;*/
    color: white;
    text-shadow: 4px 4px 0 black;
}
</style>

<style scoped>
.center {
    text-align: center;
}

h1 {
    font-size: 56px;
    margin-top: 20px;
}

.ejercicio {
    padding: 20px;
}

select {
    display: inline-block;
    appearance: none;
    text-align: center;
    background-color: white;
    border: none;
    font: inherit;
    outline: none;
    padding: 8px;
    width: 256px;

    border: 2px solid midnightblue;
    box-shadow: 4px 4px 0 black;
}
</style>