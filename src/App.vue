<template>
  <div class="ctr">
    <questions
      v-if="questionAnswered < questions.length"
      :questions="questions"
      :questionAnswered="questionAnswered"
      @qiestion-answer="handleAnswer"
    />
    <results v-else :totalCorrect="totalCorrect" :results="results" />
    <button type="button" class="reset-btn">Reset</button>
  </div>
</template>

<script>
import Questions from "./components/Questions.vue";
import Results from "./components/Results.vue";
export default {
  name: "App",
  components: {
    Questions,
    Results,
  },

  data() {
    return {
      totalCorrect: 0,
      questionAnswered: 0,
      questions: [
        {
          q: "What is 2 + 2?",
          answers: [
            {
              text: "4",
              is_correct: true,
            },
            {
              text: "3",
              is_correct: false,
            },
            {
              text: "Fish",
              is_correct: false,
            },
            {
              text: "5",
              is_correct: false,
            },
          ],
        },
        {
          q: 'How many letters are in the word "Banana"?',
          answers: [
            {
              text: "5",
              is_correct: false,
            },
            {
              text: "7",
              is_correct: false,
            },
            {
              text: "6",
              is_correct: true,
            },
            {
              text: "12",
              is_correct: false,
            },
          ],
        },
        {
          q: "Find the missing letter: C_ke",
          answers: [
            {
              text: "e",
              is_correct: false,
            },
            {
              text: "a",
              is_correct: true,
            },
            {
              text: "i",
              is_correct: false,
            },
          ],
        },
      ],
      results: [
        {
          min: 0,
          max: 2,
          title: "Try again!",
          desc: "Do a little more studying and you may succeed!",
        },
        {
          min: 3,
          max: 3,
          title: "Wow, you're a genius!",
          desc: "Studying has definitely paid off for you!",
        },
      ],
    };
  },
  methods: {
    handleAnswer(answer) {
      if (answer) {
        this.totalCorrect++;
      }
      this.questionAnswered++;
    },
  },
};
</script>

<style lang="scss" scoped></style>
