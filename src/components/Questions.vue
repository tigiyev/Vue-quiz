<template>
	<h5 @click="test()">Debug</h5>

	<div class="block" v-for="i in questionList">
		<h1 class="question">{{ i.question }}</h1>
		<div class="answer" v-for="y in i.answerList"> - {{ y.text }}</div>
	</div>
</template>

<script>
export default {
	props: ['questionList'],
	methods: {
		test() {
			console.log(this.questionList);
			console.log(this.questionList[i].answerList);
			console.log(this.i);
			console.log(this.e);
		}
	}
}
</script>

<style></style>