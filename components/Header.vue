<template>
	<header class="header">
		<div class="header__region header__region--flip">
			<h1>
				<nuxt-link to="/">Teemu Karppinen</nuxt-link>
			</h1>
			<a href="https://temetias.github.io">
				<Logo class="logo" />
			</a>
		</div>
		<nav class="header__region nav">
			<nuxt-link class="nav__item"
				to="/about">
				About
			</nuxt-link>
			<nuxt-link class="nav__item"
				to="/uses">
				Uses
			</nuxt-link>
		</nav>
	</header>
</template>

<script>
import Logo from "~/components/Logo.vue";

export default {
	components: {
		Logo,
	},
};
</script>

<style lang="scss" scoped>
@import "@/layouts/theme.scss";

$header-height: 60px;

.header {
	display: flex;
	justify-content: space-between;
	align-items: center;
	height: $header-height;

	.logo {
		width: $header-height;
	}

	&__region {
		display: flex;
		align-items: center;

		&--flip {
			flex-direction: row-reverse;
		}
	}
}

.nav {
	height: 100%;

	&__item {
		display: flex;
		align-items: center;
		height: 100%;
		padding: 0 2rem;
	}
}
</style>
