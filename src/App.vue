<template>
	<h1>{{ title }}</h1>
	<b>{{ creator }}</b>
</template>

<script>
export default {
	name: "App",
	data() {
		return {
			title: "Vue App 1.0.0 ☺️",
			creator: "Léland Shirley",
		};
	},
};
</script>

<style lang="sass">
#app
	font-family: Avenir, Helvetica, Arial, sans-serif
	-webkit-font-smoothing: antialiased
	-moz-osx-font-smoothing: grayscale
	text-align: center
	color: #2c3e50
	margin-top: 60px
</style>
