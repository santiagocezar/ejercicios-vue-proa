<script setup lang="ts">
import Ejercicio1 from "./components/Ejercicio1.vue";
import Ejercicio2 from "./components/Ejercicio2.vue";
import Ejercicio3 from "./components/Ejercicio3.vue";

</script>

<template>
<h1>Recortes de ejercicios</h1>
    <h2>Ejercicio 1</h2>
    <Ejercicio1 />
    <h2>Ejercicio 2</h2>
    <Ejercicio2 />
    <h2>Ejercicio 3</h2>
    <Ejercicio3 />
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
    background-color: aliceblue;
    /*background-image: url("/assets/caprincho.jpg");
    background-size: cover;
    background-position: center;*/
    color: #020103;
}
</style>

<style scoped>
h1,h2 {
    text-align: center;
    font-size: 56px;
    margin-top: 20px;
}
h2 {
    text-align: center;
    font-size: 48px;
    padding-top: 20px;
    border-top: dashed 2px midnightblue;
}
</style>