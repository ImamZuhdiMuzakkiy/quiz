<script setup>
import { defineProps } from 'vue';
const { questionPage, barPercentage } = defineProps(['questionPage', 'barPercentage']);
</script>

<template>
    <header>
        <h4>Questions {{ questionPage }}</h4>
        <div class="bar">
            <div class="bar-progress" :style="{ width: barPercentage }"></div>
        </div>
    </header>
</template>

<style scoped>
    header {
        margin-top: 30px;
        margin-bottom: 10px;
    }

    header h4 {
        margin: 0px;
        font-weight: normal;
    }

    .bar {
        width: 100%;
        height: 10px;
        background-color: #c9c9c9a9;
        border-radius: 5px;
        margin-top: 5px;
    }

    .bar-progress {
        width: 0%;
        height: 10px;
        background-color: #4caf50;
        border-radius: 5px;
    }
</style>