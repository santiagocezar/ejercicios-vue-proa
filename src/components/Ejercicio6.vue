<script setup lang="ts">
import { ref } from "vue";
import Base from "./util/Base.vue";
import Button from "./util/Button.vue";

interface Item {
    id: number;
    name: string;
    amount: number;
}

const list = ref<Item[]>([])
const lastID = ref(0)
const newName = ref('')
const newAmount = ref(0)

function addNewItem() {
    list.value = [{
        id: lastID.value++,
        name: newName.value,
        amount: newAmount.value,
    }, ...list.value]

    newName.value = ''
    newAmount.value = 0
}

function deleteItem(id: number) {
    const idx = list.value.findIndex(v => v.id == id)

    list.value.splice(idx, 1)
}
</script>

<template>
    <Base>
        <h2 style="margin-bottom: -10px;">Lista de compras: The Trilogy</h2>
        <h3>DEFINITIVE EDITION</h3>
        <div class="calc">
            <input v-model="newName" type="text" @keypress.enter="addNewItem" />
            <input
                class="smol"
                v-model.number="newAmount"
                type="number"
                @keypress.enter="addNewItem"
            />
            <Button @click="addNewItem">+</Button>
        </div>
        <ul v-if="list.length">
            <li v-for="item in list">
                <Button @click="deleteItem(item.id)">borrar</Button>
                {{ item.name }} ×{{ item.amount }}
            </li>
        </ul>
        <p v-else class="big">Vacío</p>
    </Base>
</template>

<style scoped>
.calc {
    display: flex;
    gap: 8px;
}
.smol {
    width: 64px;
}
input {
    width: unset;
}
</style>