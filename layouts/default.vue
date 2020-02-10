<template>
	<div class="layout">
		<Header class="layout__header" />
		<div class="layout__content content"
			id="main-content">
			<div class="content__wrap">
				<nuxt />
			</div>
			<Footer class="content__footer"/>
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
	}
}

.content {
	height: calc(100vh - 60px);
	overflow-y: scroll;

	&__wrap {
		padding: 2rem;
	}

	&__footer {
		background-color: $theme-bg-color-alt;
	}
}
</style>
