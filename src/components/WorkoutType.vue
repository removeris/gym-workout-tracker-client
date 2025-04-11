<template>
    <div class="modal-wrapper">
        <div class="modal-container">
            <h2>WORKOUT TYPE</h2>
            <div class="selection-container">
                <div class="selection-box">
                    CHEST + SHOULDERS
                </div>
                <div class="selection-box">
                    ARMS
                </div>
                <div class="selection-box">
                    BACK
                </div>
                <div class="selection-box">
                    LEGS
                </div>
            </div>
        </div>
        <i class="fa-solid fa-xmark"></i>
    </div>
</template>

<script setup lang="ts">

</script>

<style lang="css" scoped>

.modal-wrapper {
    min-width: 99%;
    min-height: 99%;
    position: absolute;
    background-color: rgba(0, 0, 0, 0.7);
    display: flex;
    justify-content: center;
    align-items: center;
}

.modal-container {
    width: 100%;

    display: flex;
    flex-direction: column;
    align-items: center;

    padding: 50px;
    margin-top: -20%;
}

.selection-container {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: stretch;
    flex-wrap: wrap;
    gap: 15px;
}

h2 {
    font-weight: 400;
    font-size: 1.5em;
    margin-bottom: 50px;
}

.selection-box {
    flex-shrink: 0;
    padding: 15px;
    width: 45%;
    min-height: 140px;
    border: 1px solid #444444;
    border-radius: 3px;
    color: #B0B0B0;
    text-align: center;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: background-color 0.2s ease-in-out;
}

.selection-box:hover {
    background-color: rgba(255, 255, 255, 0.03);
    cursor: pointer;
}

.fa-xmark {
    position: absolute;
    top: 30px;
    right: 30px;
    font-size: 40px;
    color: #B0B0B0;
}

</style>