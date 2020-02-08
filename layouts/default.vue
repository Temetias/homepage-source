<template>
	<div class="layout">
		<Header />
		<nuxt />
		<Footer class="layout__footer"/>
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
	min-height: 100vh;
	
	&__footer {
		position: absolute;
		bottom: 0;
		right: 0;
		left: 0;
	}
}

</style>
