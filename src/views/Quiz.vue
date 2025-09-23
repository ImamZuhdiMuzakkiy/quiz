<script setup>
import QuizHeader from '@/components/QuizHeader.vue';
import QuizContent from '@/components/QuizContent.vue'; 
import { useRoute } from 'vue-router';
import { ref } from 'vue';
import quizes from '../data/quizes.json';

const route = useRoute();
const quizId = parseInt(route.params.id);
const quiz = quizes.find(q => q.id === quizId);

const currentQuestionIndex = ref (0);
</script>

<template>
    <QuizHeader/>
    <QuizContent :question="quiz.questions[currentQuestionIndex]" />
</template>

<style scoped>

</style>

