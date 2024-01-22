<template>
	<h5>Your result is {{ totalCorrect }}</h5>

	<!-- <div>Questions answered {{ questionsAnswered }}</div> -->
	<!-- <div>Correct answers {{ totalCorrect }}</div> -->

	<h2 v-if="totalCorrect >= 2"> You are meme lord!</h2>
	<h2 v-else> You are healthy human being and don't know memes</h2>
</template>

<script>
export default {
	props: ['questionsAnswered', 'totalCorrect']
}
</script>

<style></style>