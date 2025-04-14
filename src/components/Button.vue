<script setup>
import { defineProps } from "vue";
defineProps({
    handleClick: {
        type: Function,
        required: true,
    },
    active: {
        type: Boolean,
        required: true,
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
    padding: 8px 15px;
    border-radius: 20px;
    cursor: pointer;
    border: 3px solid transparent;
    font-size: 13px;
}

button:hover {
    outline: 2px solid var(--red-500);
}

button.active {
    background-color: var(--red-500);
    color: var(--neutral-900);
    outline: none;
}

button.inactive {
    background-color: var(--neutral-700);
    color: var(--neutral-0);
}
</style>
