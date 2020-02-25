<template>
	<div class="logo">
		<svg class="svg"
			viewBox="0 0 130 100"
			xlmns="http://www.w3.org/2000/svg">
			<defs>
				<filter id="shadow">
					<feDropShadow dx=".2" dy=".2" stdDeviation=".7" flood-opacity=".6"/>
				</filter>
			</defs>
			<polygon class="t offset"
				points="10,0 104,0 92,10 55,10 55,100 45,100 45,10 0,10"
				style="transform: translate(2px, 3px); fill: #14a67c;"
			/>
			<polygon class="k offset"
				points="120,0 64,50 120,100 106,100 48,50 106,0"
				style="transform: translate(2px, 3px); fill: #14a67c;"
			/>
			<polygon class="dash offset"
				points="60,41 54,46 54,30 48,45 48,55 54,60 54,54 60,59"
				style="transform: translate(2px, 3px); fill: #14a67c;"
			/>
			<polygon class="t"
				points="10,0 104,0 92,10 55,10 55,100 45,100 45,10 0,10"
				style="fill: #ff652f;"
			/>
			<polygon class="k"
				points="120,0 64,50 120,100 106,100 48,50 106,0"
				style="fill: #ff652f;"
			/>
			<polygon class="dash"
				style="fill: #ff652f;"
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

		.t, .k {
			filter: url(#shadow);
		}

		.dash {
			stroke: $logo-color;

			&.offset {
				stroke: $logo-color-alt;
			}
		}
	}
}
</style>
