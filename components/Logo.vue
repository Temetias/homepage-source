<template>
	<div class="logo">
		<svg class="svg"
			viewBox="0 0 100 100"
			xlmns="http://www.w3.org/2000/svg">
			<polygon class="t"
				points="0,0 100,0 100,10 45,10 45,100 35,100 35,10 0,10"
			/>
			<polygon class="k"
				points="100,12 60,60 100,100 86,100 46,60 86,12"
			/>
		</svg>
	</div>
</template>

<style lang="scss" scoped>
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

		.t, .k {
			fill: white;
			stroke-width: 1;
			stroke: gray;
		}
	}
}
</style>