<template>
	<div class="quiz">
		<h5>Your result is: {{ totalCorrect }} / {{ questionsAnswered }} </h5>
		<h2 v-if="totalCorrect >= 2"> You are meme lord!</h2>
		<h2 v-else> You are healthy human being and don't know memes!</h2>
	</div>
</template>

<script>
export default {
	props: ['questionsAnswered', 'totalCorrect']
}
</script>

<style></style>