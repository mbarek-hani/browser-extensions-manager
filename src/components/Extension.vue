<script setup>
import Button from "./Button.vue";
import ToggleButton from "./ToggleButton.vue";

const props = defineProps(["logo", "name", "description", "isActive"]);
const emit = defineEmits("changeState");

function changeExtensionState() {
    emit("changeState", props.name);
}
</script>

<template>
    <div class="extension">
        <div class="top">
            <div class="left-side">
                <img :src="props.logo" />
            </div>
            <div class="right-side">
                <h3 class="title">{{ props.name }}</h3>
                <p class="decription">
                    {{ props.description }}
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
                <ToggleButton
                    :isChecked="props.isActive"
                    :handleChange="changeExtensionState"
                />
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
    height: 165px;
    justify-content: space-between;
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
    margin-top: -3px;
}
</style>
