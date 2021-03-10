<template>
	<h1>{{ title }}</h1>
	<b>by {{ creator }}</b>
	<br /><br />
	<button @click="toggleModal">hello (dark mode)</button>
	<button @click="toggleModalTwo">my info (default)</button>
	<!-- Modal -->
	<teleport to="#modals" v-if="showModal">
		<Modal theme="dark" @close="toggleModal">
			<!-- SLOT -->
			<h1>{{ header }}</h1>
			<b>{{ text }}</b>
			<template v-slot:links>
				<a href="#">sign up</a>
				<a href="#">log in</a>
			</template>
		</Modal>
	</teleport>

	<!-- Second Modal -->
	<teleport to="#modals" v-if="showModalTwo">
		<Modal @close="toggleModalTwo">
			<!-- SLOT -->
			<h1>User Information</h1>
			<p>Name: {{ creator }}</p>
			<p>Role: {{ role }}</p>
			<p>Username: {{ username }}</p>
			<template v-slot:moreInfo>
				<b>More:</b>
				<p>Joined: {{ startDate }}</p>
				<p>Email: {{ email }}</p>
				<p>Manager: {{ manager }}</p>
				<p>Password: ******</p>
			</template>
		</Modal>
	</teleport>
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
			title: "Vue Modal App v1.0",
			creator: "Léland Shirley",
			role: "Jr. Web Developer",
			username: "lelandshir98",
			email: "leland@shir.ley",
			manager: "Kaela C.",
			header: "Hello, there!",
			startDate: "March 8th, 2021",
			text: "Join Us At Envoy Studios, Inc.",
			showModal: false,
			showModalTwo: false,
		};
	},
	methods: {
		toggleModal() {
			this.showModal = !this.showModal;
		},
		toggleModalTwo() {
			this.showModalTwo = !this.showModalTwo;
		},
	},
};
</script>

<style lang="sass">
@import "../src/styles/global.sass"
body
  margin: 0
  padding: 0

button
  margin: 0 2% 0 2%
</style>
