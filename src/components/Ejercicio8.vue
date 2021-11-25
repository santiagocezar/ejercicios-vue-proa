<script setup lang="ts">
import { ref, computed } from "vue";
import Base from "./util/Base.vue";
import Button from "./util/Button.vue";

interface Item {
    id: number;
    name: string;
    amount: number;
}

const amount = ref(0)
const amountWithDiscount = computed(
    () => amount.value > 3500 ? amount.value * .9 : amount.value
)
const formatted = computed(
    () => amountWithDiscount.value.toFixed(2)
)

</script>

<template>
    <Base>
        <h2 style="margin-bottom: -10px;">SUPER PROMO</h2>
        <input class="smol" v-model.number="amount" type="number" />
        Total: ${{ formatted }}
    </Base>
</template>
