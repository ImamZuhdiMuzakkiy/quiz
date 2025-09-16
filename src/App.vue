<script setup>
import { ref } from "vue";
import srcQuiz from "./data/quizes.json";

const quizes = ref(srcQuiz);

</script>

<template>
  <main>
    <header>
      <h1 id="title">Quiz</h1>
      <input type="text" id="search-input">
    </header>
    <section id="quiz-container">
      <div v-for="quiz in quizes" :key="quiz.id" class="card">
        <img 
        :src="quiz.img" 
        :alt="quiz.title"
        />
        <div class="card-body">
          <h2>{{ quiz.title }}</h2>
          <p>{{ quiz.questions.length }} Questions</p>
        </div>
      </div>
    </section>
  </main>
</template>

<style scoped>
  main {
    max-width: 900px;
    margin: 0px;
  }

  header {
    margin-top: 30px;
    margin-bottom: 10px;
    display: flex;
    align-items: center;
  }

  #title {
    font-weight: bold;
    margin-right: 30px;
  }

  #search-input {
    border: none;
    background-color: #c9c9c9a9;
    padding: 10px;
    border-radius: 5px;
  }

  #quiz-container {
    display: flex;
    flex-wrap: wrap;
    margin-top: 20px;
  }

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
