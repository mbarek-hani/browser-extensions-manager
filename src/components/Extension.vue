<script setup>
import Button from "./Button.vue";

defineProps(["logo", "name", "description", "isActive"]);
</script>

<template>
    <div class="extension">
        <div class="top">
            <div class="left-side">
                <img :src="logo" />
            </div>
            <div class="right-side">
                <h3 class="title">{{ name }}</h3>
                <p class="decription">
                    {{ description }}
                </p>
            </div>
        </div>
        <div class="bottom">
            <div class="remove-btn-wrapper">
                <Button :handleClick="undefined" :active="undefined"
                    >Remove</Button
                >
            </div>
            <div class="activate-btn-wrapper">
                <Button :active="isActive">test</Button>
            </div>
        </div>
    </div>
</template>

<style scoped>
.extension {
    background-color: var(--neutral-800);
    border-radius: 15px;
    padding: 20px;
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.top {
    display: flex;
    gap: 10px;
}

.bottom {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.right-side {
    font-size: 0.8em;
    color: var(--neutral-0);
}

.left-side img {
    width: 40px;
}

.title {
    margin-bottom: 3px;
    margin-top: -5px;
}
</style>
