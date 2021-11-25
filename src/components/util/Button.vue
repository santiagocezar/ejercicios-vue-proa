<template>
    <button>
        <slot></slot>
    </button>
</template>

<style scoped>
button {
    --bg: midnightblue;
    --fg: white;
    --sh: lightcoral;
    appearance: none;
    border: none;
    font: inherit;
    outline: none;
    background-color: var(--bg);
    color: var(--fg);
    padding: 8px 16px;
    border: 2px solid var(--fg);
    box-shadow: 4px 4px 0 var(--sh);
    transition: translate 0.2s ease, box-shadow 0.2s ease;
}
button:hover {
    translate: -1px -1px;
    box-shadow: 6px 6px 0 var(--sh);
}
button:active,
button:disabled {
    translate: 2px 2px;
    box-shadow: 0px 0px 0 var(--sh);
}
button:disabled {
    opacity: 0.5;
}
</style>