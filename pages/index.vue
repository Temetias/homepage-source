<template>
	<div class="main">
		<header id="lander">
			<Logo class="index-logo"/>
			<h2>Hello.</h2>
			<h2>My name is Teemu Karppinen. I'm a full stack developer.</h2>
		</header>
	</div>
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
