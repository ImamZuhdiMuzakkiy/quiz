<script setup>
import { defineProps } from 'vue';
const { question } = defineProps(['question']);
</script>

<template>
    <section id="question-container">
        <h1 class="question-title">{{ question.text }}</h1>
    </section>
    <section id="option-container">
        <div class="option" v-for="option in question.answers" :key="option.id">
            <p class="option-label">{{ option.label }}</p>
            <p class="option-value">{{ option.text }}</p>
        </div>
    </section>
</template>

<style scoped>
    
    #question-container {
        margin-top: 30px;
    }

    .question-title {
        font-weight: bold;
        font-size: 24px;
        margin: 0px;
    }

    #opstion-container {
        margin-top: 30px;
    }

    .option {
        display: flex;
        align-items: center;
        border-radius: 5px;
        margin-bottom: 10px;
        cursor: pointer;
    }

    .option-label {
        background-color: #c9c9c9a9;
        padding: 10px;
        border-radius: 5px;
        margin: 0px;
        margin-right: 10px;
        width: 30px;
        text-align: center;
        font-weight: bold;
    }

    .option-value {
        margin: 0px;
    }
</style>