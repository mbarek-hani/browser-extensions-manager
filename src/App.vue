<script setup>
import Header from "./components/Header.vue";
import Button from "./components/Button.vue";
import { ref } from "vue";

const state = ref("all"); // all || active || inactive

function switchState(newState) {
    state.value = newState;
}
</script>

<template>
    <div class="container">
        <Header />
        <div class="options">
            <h2>Extensions List</h2>
            <div class="filters">
                <Button
                    :handleClick="
                        () => {
                            switchState('all');
                        }
                    "
                    :active="state === 'all' ? true : false"
                    >All</Button
                >
                <Button
                    :handleClick="
                        () => {
                            switchState('active');
                        }
                    "
                    :active="state === 'active' ? true : false"
                    >Active</Button
                >
                <Button
                    :handleClick="
                        () => {
                            switchState('inactive');
                        }
                    "
                    :active="state === 'inactive' ? true : false"
                    >Inactive</Button
                >
            </div>
        </div>
    </div>
</template>

<style scoped>
.container {
    max-width: 1200px;
    width: 90%;
    margin: 0 auto;
}

@media (max-width: 570px) {
    .container {
        width: 95%;
    }
}

.options h2 {
    color: var(--neutral-0);
}

.options {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.filters {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 12px;
}
</style>
