<template>
    <div class="exercise-wrapper">
        <button :class="{ 'button-active': showSelection }" @click="toggleSelection">NEW EXERCISE</button>
        <Transition name="grow">
            <div v-show="showSelection" class="exercise">
                <ul>
                    <li v-for="(elem, index) in exercises">{{ elem }}</li>
                </ul>
            </div>
        </Transition>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const props = defineProps({
    exercises: Array<string>,
})

const showSelection = ref(false);

function toggleSelection() {
    showSelection.value = !showSelection.value;
}

</script>

<style lang="css" scoped>

.exercise-wrapper {
    margin-top: 30px;
    display: flex;
    flex-direction: column;
    align-items: center;
}

button {
    width: 50%;
    padding: 10px 0px;
    background: none;
    color: #888888;
    border: solid 0.5px #444444;
    transition: background-color 0.3s ease-in-out;
    outline: none;
}

.button-active {
    background-color: rgba(136, 136, 136, 0.033);
}

.exercise {
    width: 50%;
    height: fit-content;
    background-color: rgba(136, 136, 136, 0.1);
}

li {
    color: #B0B0B0;
    padding: 8px 15px;
    list-style: none;
    border: 0.5px solid #444444;
    transition: background-color 0.3s ease-in-out;
    cursor: pointer;
}

li:hover {
    background-color: rgba(136, 136, 136, 0.08);
}

.grow-enter-active,
.grow-leave-active {
    transition: max-height 0.4s ease;
    overflow: hidden;
}

.grow-enter-from,
.grow-leave-to {
    max-height: 0;
}

.grow-enter-to,
.grow-leave-from {
     max-height: 300px;
}

</style>