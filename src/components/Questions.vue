<template>
  <div>
    <div class="questions-ctr">
      <div class="progress">
        <div
          class="bar"
          :style="{
            width: `${(questionAnswered / questions.length) * 100}%`,
          }"
        ></div>
        <div class="status">
          {{ questionAnswered }} out of {{ questions.length }} questions
          answered
        </div>
      </div>
      <div
        v-for="(question, index) in questions"
        class="single-question"
        v-show="questionAnswered === index"
      >
        <div class="question">{{ question.q }}</div>
        <div class="answers">
          <div
            v-for="answer in question.answers"
            @click="hnadleAnswer(answer.is_correct)"
            class="answer"
          >
            {{ answer.text }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Questions",
  props: {
    questions: {
      type: Array,
      required: true,
    },
    questionAnswered: {
      type: Number,
    },
  },
  methods: {
    hnadleAnswer(is_correct) {
      this.$emit("qiestion-answer", is_correct);
    },
  },
};
</script>

<style lang="scss" scoped></style>
