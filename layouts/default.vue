<template>
	<div class="layout">
		<Header class="layout__header" />
		<div class="layout__content content"
			id="main-content">
			<div class="content__wrap">
				<nuxt class="content__main"/>
			</div>
			<div class="content__padder"></div>
			<Footer class="footer"/>
		</div>
	</div>
</template>

<script>
import Header from "~/components/Header.vue";
import Footer from "~/components/Footer.vue";

export default {
	components: {
		Header,
		Footer,
	},
};
</script>


<style lang="scss">
@import "@/layouts/theme.scss";

.layout {
	display: flex;
	flex-direction: column;

	&__header {
		height: 60px;
		
		box-shadow: $theme-shadow;
	}
}

.content {
	height: calc(100vh - 60px);
	overflow-y: scroll;
	overflow-x: hidden;

	&__wrap {
		padding: 2rem;
		box-shadow: $theme-shadow;
		background-color: $theme-color-1;
	}

	&__padder {
		height: 30vh;
		pointer-events: none;
	}
}

@media only screen and (max-width: $screen-tablet) {
	.content__wrap {
		padding: 2rem 1.5rem;
	}
}

@media only screen and (max-width: $screen-mobile) {
	.content__wrap {
		padding: 2rem .5rem;
	}
}

.footer {
	position: absolute;
	bottom: 0;
	right: 0;
	left: 0;
	height: 30vh;
	background-color: $theme-color-3;
	z-index: -10;
}
</style>
