<template>
	<div class="box">
		<div class="box__inner"
			:class="{ image }">
			<slot></slot>
		</div>
	</div>
</template>

<script>
export default {
	props: [
		"image"
	],
};
</script>

<style lang="scss">
@import "@/layouts/theme.scss";

.box {
	background-color: $theme-color-4;
	transform: rotate(-1deg);
	box-shadow: $theme-shadow;
	margin: 0 0 10vh 30vw;
	padding: .2rem;

	&__inner {
		transform: rotate(1deg);
		padding: 1rem;
		box-shadow: $theme-shadow;
		background-color: $theme-color-3;

		&.image {
			padding: .3rem;
			margin-bottom: 3px;

			> * {
				transform: rotate(0deg);
			}
		}
	}

	&:nth-child(odd) {
		background-color: $theme-color-5;
		margin: 0 30vw 5vw 0;
		transform: rotate(1deg);

		.box__inner {
			transform: rotate(-1deg);
		}
	}
}

@media only screen and (max-width: $screen-tablet) {
	.box {
		margin: 0 0 4vh 0;

		&:nth-child(odd) {
			background-color: $theme-color-5;
			margin: 0 0 4vh 0;
		}
	}
}
</style>