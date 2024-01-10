<!-- todo -->

<!-- show oly one question at a time -->


<template>
  <div class="quiz">
    <questions :questionList="questionList">
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
    test() {
      console.log(this.questionList)
    },
    checkAnswer(y) {
      if (y.isCorrect) {
        console.log("right")
      } else console.log("wrong")
    }
  }
}
</script>

<style>
.quiz {
  outline: 1px solid #4343b3;
}
</style>
