<!--  how to show second question? -->

<template>
	<!-- <button @click="this.$parent.appTest()">Debug App</button> -->
	<!-- <button @click="test2()">Debug Questions</button> -->
	<br>

	<div>Questions answered {{ questionsAnswered }}</div>
	<div>Correct answers {{ totalCorrect }}</div>
	<br>

	<div class="block" v-for="(qBlock, index) in questionList" v-show="questionsAnswered === index">
		<h3 class="question">Continue meme: <br> <i>{{ qBlock.question }}</i></h3>
		<div class="answer" v-for="(answer, index2) in qBlock.answerList" @click="checkAnswer(answer.isCorrect)">
			- {{ answer.text }}
			<!-- {{ answer.isCorrect }} -->
			<!-- {{ index2 }} -->
		</div>

		<!-- <div @click="func(questionsAnswered)">Increase</div> -->
	</div>
</template>

<script>
export default {
	props: ['questionList', 'questionsAnswered', 'totalCorrect'],
	emits: ['question-answered'],
	methods: {
		test2() {
			console.log(this.questionList)
			console.log(this.questionsAnswered)
			console.log(this.totalCorrect)
		},
		checkAnswer(isCorrect) {
			console.log(isCorrect);
			this.$emit('question-answered', isCorrect);
		},
	}
}
</script>

<style></style>