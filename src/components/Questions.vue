<template>
	<div class="quiz">
		<!-- <button @click="this.$parent.appTest()">Debug App</button> -->
		<!-- <button @click="test2()">Debug Questions</button> -->

		<h5>Your result is: {{ totalCorrect }} / {{ questionsAnswered }} </h5>

		<transition-group name="fade">
			<div class="block" v-for="(qBlock, index) in questionList" v-show="questionsAnswered === index">
				<br>
				<h5>Continue the meme:</h5>
				<h3 class="question"><i>{{ qBlock.question }} ... </i></h3>
				<div class="answer" v-for="(answer, index2) in qBlock.answerList" @click="checkAnswer(answer.isCorrect)">
					... {{ answer.text }}
					<!-- {{ answer.isCorrect }} -->
					<!-- {{ index2 }} -->
				</div>
			</div>
		</transition-group>

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