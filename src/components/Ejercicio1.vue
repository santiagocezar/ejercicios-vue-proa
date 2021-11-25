<script setup lang="ts">
import Base from './util/Base.vue'
import { ref } from "vue";

const nombre = ref('')
</script>

<template>
    <Base>
        <h2>Jaja, saludos</h2>
        <input autofocus v-model="nombre" type="text" />
        <p class="big">Hola, {{ nombre || '...' }}</p>
    </Base>
</template>