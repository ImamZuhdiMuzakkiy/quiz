<script setup>
import QuizHeader from '@/components/QuizHeader.vue';
import QuizContent from '@/components/QuizContent.vue'; 
import QuizResult from '@/components/QuizResult.vue';
import { useRoute } from 'vue-router';
import { ref, computed } from 'vue';
import quizes from '../data/quizes.json';

const route = useRoute();
const quizId = parseInt(route.params.id);
const quiz = quizes.find(q => q.id === quizId);
const numberOfCorrectAnswers = ref(0);

const currentQuestionIndex = ref (0);
const showResult = ref(false);
const questionPage = computed(() => `${currentQuestionIndex.value + 1} / ${quiz.questions.length}`);

const barPercentage = computed(() => {
    return `${((currentQuestionIndex.value + 1) / quiz.questions.length) * 100}%`;
});

function onSelectOption(option) {
    if(option.correct) {
        numberOfCorrectAnswers.value++;
    } 
    if (currentQuestionIndex.value === quiz.questions.length - 1) {
        showResult.value = true;
        return;
    }
    currentQuestionIndex.value++;
}
</script>

<template>
    <QuizHeader :question-page="questionPage" :barPercentage="barPercentage" />
    <QuizContent v-if="!showResult" :question="quiz.questions[currentQuestionIndex]" @selectOption="onSelectOption" />
    <QuizResult v-else :quizLength="quiz.questions.length" :numberOfCorrectAnswers="numberOfCorrectAnswers" />
</template>



