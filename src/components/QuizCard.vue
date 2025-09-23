<script setup>
const { quiz } = defineProps(["quiz"]);
import { useRouter } from "vue-router";

const router = useRouter();

function goToQuiz() {
    router.push({ name: 'quiz', params: { id: quiz.id } });
}
</script>

<template>
    <div class="card" @click="goToQuiz">
        <img :src="quiz.img" :alt="quiz.title" />
        <div class="card-body">
            <h2>{{ quiz.title }}</h2>
            <p>{{ quiz.questions.length }} Questions</p>
        </div>
    </div>
</template>

<style scoped>
  .card {
    width: 270px;
    margin-right: 30px;
    margin-bottom: 30px;
    border-radius: 5px;
    overflow: hidden;
    box-shadow: 0px 0px 10px #00000029;
  }

  .card img {
    width: 100%;
    height: 150px;
    object-fit: cover;
    margin: 0px;
  }

  .card-body {
    padding: 10px;
  }

  .card-body h2 {
    margin: 0px;
    font-size: 18px;
  }
</style>