<template>
	<div class="backdrop" @click.self="closeModal">
		<div class="modal" :class="{ dark: theme === 'dark' }">
			<slot></slot>
			<div class="actions">
				<slot name="links"></slot>
				<slot name="moreInfo"></slot>
			</div>
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

<style lang="sass">
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

.modal .actions
    text-align: center
    margin: 30px 0 10px 0

.modal .actions a
    text-align: center
    // color: #fff
    background: #fff
    margin: 5%
    border: 1px solid #000
    border-radius: .3rem
    text-decoration: none
    padding: 2%
    font-weight: 500
</style>
