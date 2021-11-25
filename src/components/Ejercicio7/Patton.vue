<script setup lang="ts">
import { ref, CSSProperties } from "vue";
import Base from "../util/Base.vue";
import Button from "../util/Button.vue";

defineProps<{
    label: string;
    color: CSSProperties['color'];
    text: CSSProperties['color'];
    shadow: CSSProperties['color'];
}>()

const count = ref(0)
</script>

<template>
    <Button
        class="boton"
        :style="{ '--color': color, '--text': text, '--shadow': shadow }"
        @click="count++"
    >
        <h2>{{ label }}</h2>
        <h1>{{ count }}</h1>
    </Button>
</template>

<style scoped>
.boton {
    width: 10rem;
    height: 10rem;
    --bg: var(--color);
    --fg: var(--text);
    --sh: var(--shadow);
}
h2 {
    line-height: 1;
}
</style>