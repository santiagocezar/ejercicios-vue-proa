<template>
    <div>
        <slot></slot>
    </div>
</template>

<style scoped>
div {
    overflow: auto;

    display: flex;
    gap: 8px;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: aliceblue;
    padding: 16px;
    border: 2px solid midnightblue;
    box-shadow: 4px 4px 0 black;
    color: black;
    text-shadow: none;
}
</style>