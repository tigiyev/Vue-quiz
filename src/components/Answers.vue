<template>
	<!-- <h1>comp</h1> -->

	<!-- луп только внутри компонента -->
	<!-- <ul>
		<li v-for="y in e.answerList" @click="checkAnswer(y)">{{ y.text }}</li>
	</ul> -->
</template>

<script>
export default {
	props: ['questionList', 'answerList']
}
</script>

<style></style>