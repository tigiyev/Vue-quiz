<!-- todo -->

<!-- show oly one question at a time -->
<!-- update parent data from child by using emits ?? read about-->


<template>
  <button @click="appTest()" style="width: 100px;">Debug App</button>
  <div class="quiz">
    <questions :questionList="questionList" :questionsAnswered="questionsAnswered" :totalCorrect="totalCorrect">
    </questions>
  </div>
</template>

<script>
import questions from './components/Questions.vue';

export default {
  components: {
    questions
  },

  data() {

    return {
      questionsAnswered: 0,
      totalCorrect: 0,
      questionList: [
        {
          question: 'Hewwo everynyan. Hawayu?',
          answerList: [
            {
              text: 'Well sank you',
              isCorrect: true
            },
            {
              text: 'Wat?',
              isCorrect: false
            },
            {
              text: 'Hello to you?',
              isCorrect: false
            },
            {
              text: 'No?',
              isCorrect: false
            },
          ]
        },
        {
          question: 'Omaiwa mu shindeiru?',
          answerList: [
            {
              text: 'Nani?',
              isCorrect: true
            },
            {
              text: 'Tatakae!',
              isCorrect: false
            },
            {
              text: 'Bakara',
              isCorrect: false
            },
            {
              text: 'Nandayo',
              isCorrect: false
            },
          ]
        }

      ]


    }
  },
  methods: {
    appTest() {
      console.log(this.questionList)
      console.log(this.questionsAnswered)
      console.log(this.totalCorrect)
    },

  }
}
</script>

<style>
/* .quiz {
  outline: 1px solid #4343b3;
} */
</style>
