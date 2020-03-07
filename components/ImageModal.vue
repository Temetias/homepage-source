<template>
	<div class="image-modal"
		@click="$emit('close')">
		<header class="image-modal__header"
			@click.stop>
			<h5>{{ title }}</h5>
			<i class="fa fa-times"
				@click="$emit('close')">
			</i>
		</header>
		<img class="image-modal__displayer"
			:src="lazySrc"
			:alt="alt"
			@click.stop
		/>
	</div>
</template>

<script>
export default {
	props: [
		"src",
		"alt",
		"title",
	],
	data() {
		return {
			isMounted: false,
		};
	},
	mounted() {
		this.isMounted = true;
	},
	computed: {
		lazySrc() {
			return this.isMounted ? this.src : "";
		},
	},
};
</script>

<style lang="scss" scoped>
.image-modal {
	position: fixed;
	top: 0;
	left: 0;
	bottom: 0;
	right: 0;
	background-color: gray;
	display: flex;
	flex-direction: column;
	justify-content: space-evenly;
	align-items: center;
	z-index: 20;

	&__header {
		width: 90%;
		display: flex;
		justify-content: space-between;
		align-items: center;

		i {
			cursor: pointer;
		}
	}

	&__displayer {
		width: 90%;
	}
}
</style>
