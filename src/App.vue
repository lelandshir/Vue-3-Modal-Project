<template>
	<h1>{{ title }}</h1>
	<b>Author: {{ creator }}</b>
	<br /><br />
	<button @click="toggleModal">welcome</button>
	<!-- Modal Component -->
	<div v-if="showModal">
		<Modal :header="header" :text="text" theme="dark" @close="toggleModal" />
	</div>
</template>

<script>
import Modal from "./components/Modal";

export default {
	name: "App",
	components: {
		Modal,
	},
	data() {
		return {
			title: "Vue App 1.0.0 ☺️",
			creator: "Léland Shirley",
			header: "Hello, there!",
			text: "Join Us At Envoy Studios, Inc.",
			showModal: false,
		};
	},
	methods: {
		toggleModal() {
			this.showModal = !this.showModal;
		},
	},
};
</script>

<style lang="sass">
@import "../src/styles/global.sass"
body
  margin: 0
  padding: 0
  background-color: pink
</style>
