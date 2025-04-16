<script setup>
defineProps(["isChecked", "handleChange"]);
</script>

<template>
    <input type="checkbox" :checked="isChecked" @change="handleChange" />
</template>

<style scoped>
input {
    appearance: none;
    background-color: var(--neutral-600);
    outline: none;
    padding: 10px 20px;
    border-radius: 20px;
    cursor: pointer;
    border: 2px solid transparent;
    position: relative;
    transition: 0.3s background-color ease-in-out;
}

input:hover {
    outline: 2px solid var(--red-500);
}

input:checked {
    background-color: var(--red-500);
    outline: none;
}

input::before {
    content: "";
    position: absolute;
    left: 2px;
    top: 2px;
    bottom: 2px;
    width: 16px;
    background-color: var(--neutral-0);
    border-radius: 50%;
    transition: 0.3s all ease-in-out;
}

input:checked::before {
    left: 55%; /* changing the left property instead of setting it to auto and then set the right property to 2px for a smooth transition */
    /* right: 2px; */
}
</style>
