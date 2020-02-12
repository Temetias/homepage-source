<template>
	<div class="logo">
		<svg class="svg"
			viewBox="0 0 120 100"
			xlmns="http://www.w3.org/2000/svg">
			<polygon class="t"
				points="10,0 104,0 92,10 55,10 55,100 45,100 45,10 0,10"
			/>
			<polygon class="k"
				points="120,0 64,50 120,100 106,100 48,50 106,0"
			/>
			<polygon class="dash"
				points="60,41 54,46 54,30 48,45 48,55 54,60 54,54 60,59"
			/>
		</svg>
	</div>
</template>

<style lang="scss" scoped>
@import "@/layouts/theme.scss";

.logo {
	position: relative;

	&::after {
		content: "";
		display: block;
		padding-bottom: 100%;
	}

	.svg {
		position: absolute;
		width: 100%;
		height: 100%;

		.t, .k, .dash {
			fill: $logo-color;
			stroke-width: 1;
			stroke: $logo-color-alt;
		}

		.dash {
			stroke: $logo-color;
		}
	}
}
</style>