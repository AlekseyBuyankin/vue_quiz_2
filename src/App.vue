<template>
  <div id="app">
    <Header
      :num_total="questions.length"
      :num_current="index"
      :num_correct="num_correct"
      :reset="reset"
    />
    <b-container class="container">
      <b-row>
        <b-col sm="12" offset="0">
          <QuestionBox
            v-if="questions.length"
            :next_question="next_question"
            :current_question="questions[index]"
            :increment="increment"
            :is_reset="is_reset"
          />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import QuestionBox from "./components/QuestionBox.vue";

export default {
  name: "App",
  components: {
    Header,
    QuestionBox
  },
  data() {
    return {
      questions: [],
      index: 0,
      num_correct: 0,
      is_reset: false
    };
  },
  methods: {
    next_question() {
      this.index++;
    },
    increment(isCorrect) {
      if (isCorrect) {
        this.num_correct++;
      }
    },
    reset() {
      this.num_correct = 0;
      this.index = 0;
      this.is_reset = true;
    }
  },
  mounted() {
    fetch(
      "https://opentdb.com/api.php?amount=10&category=22&difficulty=easy&type=multiple",
      {
        method: "get"
      }
    )
      .then(response => {
        return response.json();
      })
      .then(jsonData => {
        this.questions = jsonData.results;
      });
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
