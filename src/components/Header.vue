<script setup>
import Logo from "./Logo.vue";
</script>

<template>
    <div class="header">
        <Logo color="#fff" />
        <button class="mode-icon-wrapper">
            <img src="../assets/images/icon-sun.svg" />
        </button>
    </div>
</template>

<style scoped>
.header {
    background-color: var(--neutral-800);
    height: 65px;
    border-radius: 15px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 10px;
    margin: 20px 0;
}

.mode-icon-wrapper {
    background-color: var(--neutral-700);
    padding: 13px;
    display: grid;
    place-items: center;
    border-radius: 15px;
    cursor: pointer;
    transition: 0.3s background-color ease;
    outline: none;
    border: 3px solid transparent;
}

.mode-icon-wrapper:hover {
    background-color: var(--neutral-600);
    outline: 2px solid var(--red-500);
}
</style>
