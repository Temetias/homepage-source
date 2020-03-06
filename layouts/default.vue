<template>
	<div class="layout">
		<Header class="layout__header" />
		<div class="layout__content content"
			id="main-content">
			<Footer class="footer"/>
			<div class="content__wrap">
				<nuxt class="content__main"/>
			</div>
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
	position: relative;

	&__header {
		height: 60px;
		background-color: $theme-color-2;
		box-shadow: $theme-shadow;
	}
}

.content {
	height: calc(100vh - 60px);
	overflow-y: scroll;
	overflow-x: hidden;

	&__wrap {
		background: linear-gradient($theme-color-1, $theme-color-1);
		padding: 2rem;
		margin-bottom: 30vh;
		box-shadow: $theme-shadow;

		p {
			z-index: 10;
		}
	}
}

.footer {
	position: fixed;
	bottom: 0;
	right: 0;
	left: 0;
	height: 30vh;
	background-color: $theme-color-2;
	z-index: -10;
}
</style>
