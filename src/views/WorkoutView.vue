<template>

<WorkoutType v-if="showWorkoutTypeModal" @selectedType="handleTypeSelection"  />

<h2>{{ selectedWorkoutType }}</h2>

<div class="selected-exercises">
    <div class="exercise-block" v-for="(elem, index) in selectedExercises">
        <h4>{{ elem }}</h4>
        <ul>
        </ul>
        <div @click="addNewSet(elem)"> 
            <i class="fa-solid fa-plus"></i>
            <span>CLICK TO ADD A SET</span>
        </div>
    </div>
</div>

<Exercise :exercises="exercisesProp" @selectedExercise="handleExerciseSelection" />

</template>

<script setup lang="ts">
import { ref } from 'vue';

import WorkoutType from '@/components/WorkoutType.vue';
import Exercise from '@/components/Exercise.vue';

const exercisesProp = ref<string[]>([]);
const selectedExercises = ref<string[]>([]);

const backExercises = [ "Lat Pulldown", "Mid-back Row", "Lower Back"];
const chestShouldersExercises = [ "Incline Chest", "Chest Press", "Chest Fly", "Shoulder Press", "Lateral Raise", "Rear Delts"];
const armsExercises = [ "Tricep Pushdown", "Skullcrushers", "Single-arm Pushdown", "Bicep Curl", "Cable Bicep Curl", "Cable Hammer-curls"];

const showWorkoutTypeModal = ref(true);
const selectedWorkoutType = ref<string | null>(null);

const handleTypeSelection = (type: string) => {
    selectedWorkoutType.value = type;
    showWorkoutTypeModal.value = false;

    switch(type) {
        case "BACK":
            exercisesProp.value = backExercises;
            break;
        case "ARMS":
            exercisesProp.value = armsExercises;
            break;
        case "CHEST + SHOULDERS":
            exercisesProp.value = chestShouldersExercises;
            break;
        default:
            exercisesProp.value = [];
    }
}

const handleExerciseSelection = (selection: string) => {
    if(!selectedExercises.value.includes(selection)) {
        selectedExercises.value.push(selection);
    }
}

function addNewSet(elem: string) : void {
}

</script>

<style lang="css" scoped>

h2 {
    margin-top: 20px;
}

.exercise-block {
    padding: 8px 20px;
}

h4 {
    text-align: left;
    margin-bottom: 10px;
}

.fa-plus {
    color: #888888;
    padding: 10px;
}

span {
    color: #888888;
}

</style>