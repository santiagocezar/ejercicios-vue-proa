<script setup lang="ts">
import { ref } from "vue";
import Base from "../util/Base.vue";
import Button from "../util/Button.vue";
import Patton from "./Patton.vue";

</script>

<template>
    <Base>
        <h2 style="margin-bottom: -10px;">EmpanadApp</h2>
        <div class="calc">
            <Patton label="Jamón y Queso" color="#f89" text="black" shadow="#ea0"></Patton>
            <Patton label="Carne Salada" color="#e23" text="white" shadow="#a02"></Patton>
            <Patton label="Carne Dulce" color="#e28" text="white" shadow="#a06"></Patton>
            <Patton label="Pitusas" color="#ec8" text="black" shadow="#e6f"></Patton>
            <Patton label="Pescado" color="salmon" text="black  " shadow="teal"></Patton>
        </div>
    </Base>
</template>

<style scoped>
.calc {
    margin-top: 1rem;
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    gap: 8px;
}
.smol {
    width: 64px;
}
input {
    width: unset;
}
</style>