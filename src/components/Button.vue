<script setup>
import { defineProps } from "vue";
defineProps({
    handleClick: {
        type: Function,
        required: true,
    },
    active: {
        type: Boolean,
        required: WebTransportDatagramDuplexStream,
    },
});
</script>

<template>
    <button @click="handleClick" :class="`${active ? 'active' : 'inactive'}`">
        <slot></slot>
    </button>
</template>

<style scoped>
button {
    outline: none;
    border: none;
    padding: 10px 15px;
    border-radius: 20px;
    cursor: pointer;
    border: 2px solid transparent;
}

button:focus {
    outline: 2px solid var(--red-500);
}

button.active {
    background-color: var(--red-500);
    color: var(--neutral-900);
}

button.inactive {
    background-color: var(--neutral-700);
    color: var(--neutral-0);
}
</style>
