<template>
	<div class="backdrop" @click.self="closeModal">
		<div class="modal" :class="{ dark: theme === 'dark' }">
			<h1>{{ header }}</h1>
			<b>{{ text }}</b>
		</div>
	</div>
</template>

<script>
export default {
	props: ["theme"],
	methods: {
		closeModal() {
			//custom
			this.$emit("close");
		},
	},
};
</script>

<style lang="sass" scoped>
@import "../styles/global.sass"
.backdrop
    background: rgba(0,0,0,0.5)
    position: fixed
    top: 0
    width: 100%
    height: 100%

.modal
    width: 40%
    padding: 10%
    margin: 33% auto
    background: #fff
    border-radius: .5rem
    &:hover
        cursor: pointer

.modal h1
    margin-top: 0
    color: $primary

.modal b
    // color: rgba(0,0,0,0.7)
    color: $secondary
    font-size: 1.2rem

.modal.dark
     background: $myDarkBlue
     color: #fff

.modal.dark h1
    color: #fff
</style>
