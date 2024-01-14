<template>
	<!-- <h5 @click="test2()">Debug</h5> -->
	<h5 @click="this.$parent.test()">Debug</h5>

	<div class="block" v-for="qBlock in questionList">
		<h1 class="question">{{ qBlock.question }}</h1>
		<div class="answer" v-for="question in qBlock.answerList" @click="checkAnswer(question)" v-show="question.isCorrect">
			{{ question.text }}
		</div>

		<!-- <div v-if="checkAnswer(question) == true"> correct!</div> -->


		<!-- <p v-if="false">true</p>
		<p v-else-if="'aaa' == 'aaa'">else if</p>
		<p v-else>else</p>
		<div v-show="true">show must go on</div>
		<div v-show="false">show must NOT go on</div> -->


	</div>
</template>

<script>
export default {
	props: ['questionList'],
	methods: {
		test2() {
			// console.log(this.questionList);
			// console.log(this.questionList[i].answerList);
			console.log(this.i);

		},
		checkAnswer(question) {
			if (question.isCorrect) {
				console.log("right")
			} else console.log("wrong")
		},
		func() {

			console.log('hewwo!');

		}
	}
}
</script>

<style></style>