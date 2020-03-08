<template>
	<div class="loader">
		<div class="loader__1"></div>
		<div class="loader__2"></div>
	</div>
</template>

<style lang="scss" scoped>
@import "@/layouts/theme.scss";

.loader {
	height: .3rem;
	display: flex;

	&__1 {
		flex: 1;
		height: .3rem;
		animation: loader-1 1.2s -.6s linear infinite;
		background: linear-gradient(to left, $theme-color-5, $theme-color-4);
		transform-origin: right;
		margin-right: -1px;
	}

	&__2 {
		flex: 1;
		height: .3rem;
		animation: loader-2 1.2s linear infinite;
		background: linear-gradient(to left, $theme-color-4, $theme-color-5);
		transform-origin: right;
	}
}

@keyframes loader-1 {
	0% {
		transform: scaleX(0);
	} 25% {
		transform: scaleX(1);
		transform-origin: right;
	} 26% {
		transform: scaleX(1);
		transform-origin: left;
	} 50% {
		transform: scaleX(0);
		transform-origin: left;
	} 75% {
		transform-origin: left;
		transform: scaleX(1);
	} 76% {
		transform-origin: right;
		transform: scaleX(1);
	} 100% {
		transform: scaleX(0);
	}
}

@keyframes loader-2 {
	0% {
		transform: scaleX(0);
	} 25% {
		transform: scaleX(1);
		transform-origin: right;
	} 26% {
		transform: scaleX(1);
		transform-origin: left;
	} 50% {
		transform: scaleX(0);
		transform-origin: left;
	} 75% {
		transform-origin: left;
		transform: scaleX(1);
	} 76% {
		transform-origin: right;
		transform: scaleX(1);
	} 100% {
		transform: scaleX(0);
	}
}
</style>