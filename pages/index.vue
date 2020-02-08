<template>
	<main>
		<header>
			<Logo class="index-logo"/>
			<h2>Hello world.</h2>
		</header>
	</main>
</template>

<script>
import Logo from "~/components/Logo.vue";

export default {
	components: {
		Logo,
	},
};
</script>

<style lang="scss">
@import "@/layouts/theme.scss";

.index-logo {
	width: 10vw;
}
</style>
