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
@import "../src/styles/global.sass"
body
  background-color: pink
</style>
