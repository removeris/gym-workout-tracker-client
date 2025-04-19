<template>

<WorkoutType v-if="showWorkoutTypeModal" @selectedType="handleTypeSelection"  />

<h2>{{ selectedWorkoutType }}</h2>

<Exercise :exercises="exercisesProp" />

<div class="selected-exercises">

</div>


</template>

<script setup lang="ts">
import { ref } from 'vue';

import WorkoutType from '@/components/WorkoutType.vue';
import Exercise from '@/components/Exercise.vue';

const showWorkoutTypeModal = ref(true);
const selectedWorkoutType = ref<string | null>(null);

const backExercises = [ "Lat Pulldown", "Mid-back Row", "Lower Back"];
const chestShouldersExercises = [ "Incline Chest", "Chest Press", "Chest Fly", "Shoulder Press", "Lateral Raise", "Rear Delts"];
const armsExercises = [ "Tricep Pushdown", "Skullcrushers", "Single-arm Pushdown", "Bicep Curl", "Cable Bicep Curl", "Cable Hammer-curls"];

const exercisesProp = ref<string[]>([]);
const selectedExercises = ref<string[]>([]);

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

</script>

<style lang="css" scoped>

h2 {
    margin-top: 20px;
}

</style>