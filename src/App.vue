<script setup>
import Header from "./components/Header.vue";
import Button from "./components/Button.vue";
import Extension from "./components/Extension.vue";

import { ref } from "vue";

import { extensions } from "./data";
import Logo from "./components/Logo.vue";

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
        <main class="extensions">
            <Extension
                v-for="extension in extensions"
                :logo="extension.logo"
                :name="extension.name"
                :description="extension.description"
                :isActive="extension.isActive"
            />
        </main>
    </div>
</template>

<style scoped>
.extensions {
    margin-top: 15px;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 8px;
}

@media (max-width: 980px) {
    .extensions {
        grid-template-columns: 1fr 1fr;
        row-gap: 8px;
        column-gap: 20px;
    }
}

@media (max-width: 665px) {
    .extensions {
        grid-template-columns: 1fr;
        row-gap: 8px;
    }
}
/* end */
.container {
    max-width: 1200px;
    width: 90%;
    margin: 0 auto;
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

@media (max-width: 570px) {
    .container {
        width: 95%;
    }
    .options {
        flex-direction: column;
        justify-content: flex-start;
        gap: 15px;
    }
}
</style>
