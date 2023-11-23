<!-- todo -->
<!-- Разбить на модули -->
<!-- сделать квиз рабочим -->
<!-- добавить квизу прогрессии -->
<!-- добавить результат  -->
<!-- если 2 ответа правильные = success text
else = fail text  -->

<!-- понять что такое v-bind -->

<template>
  <div class="quiz">

    <div v-for="e in questionList">
      <h1>{{ e.question }}</h1>

      <answers></answers>

      <ul>
        <li v-for="y in e.answerList" @click="checkAnswer(y)">{{ y.text }}</li>
      </ul>
    </div>

  </div>
</template>

<script>
import answers from './components/Answers.vue';
// import Answers from 'components/Answers.vue';

export default {
  components: {
    answers
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
