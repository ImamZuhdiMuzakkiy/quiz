<script setup>
    import { defineProps } from 'vue';
    import { RouterLink } from 'vue-router';
    const { quizLength, numberOfCorrectAnswers } = defineProps(['quizLength', 'numberOfCorrectAnswers']);
</script>

<template>
    <section class="results">
        <p>Score:</p>
        <h1>{{ numberOfCorrectAnswers }} / {{ quizLength }}</h1>
        <RouterLink to="/">Take the quiz again</RouterLink>
    </section>
</template>

<style scoped>
.results {
    margin-top: 50px;
    text-align: center;
}  
p {
    margin: 0px;
    font-size: 24px;
}
h1 {
    font-size: 48px;
    margin: 10px 0px;
}
</style>