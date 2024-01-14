<template>
	<!-- <button @click="this.$parent.appTest()">Debug App</button> -->
	<button @click="test2()">Debug Questions</button>
	<br>

	<div>Questions answered {{ questionsAnswered }}</div>
	<div>Correct answers {{ totalCorrect }}</div>
	<br>

	<div class="block" v-for="qBlock in questionList">
		<h3 class="question">{{ qBlock.question }}</h3>
		<div class="answer" v-for="(question, index) in qBlock.answerList" @click="checkAnswer(question, questionsAnswered)">
			{{ question.text }}
			{{ index }}
		</div>

		<div @click="func(questionsAnswered)">Increase</div>


		<button>Reset</button>



	</div>
</template>

<script>
export default {
	props: ['questionList', 'questionsAnswered', 'totalCorrect'],
	// ??
	emits: ['questionsAnswered', 'totalCorrect'],
	// ??
	methods: {
		test2() {
			console.log(this.questionList)
			console.log(this.questionsAnswered)
			console.log(this.totalCorrect)

		},
		checkAnswer(question, questionsAnswered) {
			if (question.isCorrect) {
				questionsAnswered = questionsAnswered + 1;
				console.log("right", questionsAnswered);
			} else console.log("wrong")
		},
		func() {
			console.log('hewwo!');
			console.log(questionsAnswered);
			// Why does not work 
		}
	}
}
</script>

<style></style>