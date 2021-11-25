<script lang="ts" setup>
import Card from './Card.vue';
</script>
<template>
    <Card>
        <slot></slot>
    </Card>
</template>
<style scoped>
::v-slotted(h2) {
    text-align: center;
    font-size: 48px;
}
::v-slotted(input),
::v-slotted(select) {
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
::v-slotted(input::-webkit-outer-spin-button),
::v-slotted(input::-webkit-inner-spin-button) {
    -webkit-appearance: none;
    margin: 0;
}
::v-slotted(input[type="number"]) {
    -moz-appearance: textfield;
}
::v-slotted(input[aria-invalid]) {
    border-color: red;
}
::v-slotted(.big) {
    font-size: 48px;
    font-weight: 300;
    text-align: center;
}
</style>