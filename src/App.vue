<!-- todo -->

<template>
  <!-- <button @click="appTest()" style="width: 100px;">Debug App</button> -->

  <div class="quiz">
    <questions v-if="questionsAnswered < questionList.length" :questionList="questionList"
      :questionsAnswered="questionsAnswered" :totalCorrect="totalCorrect" @question-answered="questionAnswered">
    </questions>

    <results v-else :questionsAnswered="questionsAnswered" :totalCorrect="totalCorrect"></results>

    <button v-if="questionsAnswered === questionList.length" @click="reset()">Reset</button>
  </div>
</template>

<script>
import Questions from './components/Questions.vue';
import Results from './components/Results.vue';

export default {
  components: {
    Questions, Results
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
    questionAnswered(isCorrect) {
      console.log(isCorrect);
      if (isCorrect) {
        this.totalCorrect++;
      }
      this.questionsAnswered++;
    },
    reset() {
      this.totalCorrect = 0;
      this.questionsAnswered = 0;
    }

  }
}
</script>

<style>
/* .quiz {
  outline: 1px solid #4343b3;
} */
</style>
