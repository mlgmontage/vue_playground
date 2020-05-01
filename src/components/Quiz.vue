<template>
  <div>
    <h3>Quiz</h3>
    <div v-for="(question, index) in questions" :key="index">
      <h5 v-html="question.question"></h5>
    </div>
  </div>
</template>

<script>
export default {
  name: "Quiz",
  data() {
    return {
      questions: null,
    };
  },
  mounted() {
    fetch("https://opentdb.com/api.php?amount=10")
      .then((response) => response.json())
      .then((jsonData) => (this.questions = jsonData.results));
  },
};
</script>
