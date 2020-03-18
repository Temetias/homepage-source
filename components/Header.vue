<template>
	<header class="header">
		<div class="
			header__region
			header__region--flip
			header__region--slider-animation
			header__region--small-screen-left">
			<h1>
				<nuxt-link class="home-link no-underline no-outline"
					to="/">
					Teemu Karppinen
				</nuxt-link>
			</h1>
			<a class="no-underline"
				href="https://teemukarppinen.dev">
				<Logo class="logo" />
			</a>
		</div>
		<nav class="header__region nav"
			:class="{ 'scrolling-down': scrollingDown }"
			ref="nav">
			<nuxt-link class="nav__item no-outline"
				to="/about">
				About
			</nuxt-link>
			<nuxt-link class="nav__item no-outline"
				to="/projects">
				Projects
			</nuxt-link>
			<nuxt-link class="nav__item no-outline"
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

<style lang="scss">
@import "@/layouts/theme.scss";

$header-height: 60px;

.header {
	display: flex;
	justify-content: space-between;
	align-items: center;
	color: $theme-color-5;
	transition: background-color .2s, box-shadow .2s;
	box-shadow: $theme-shadow;
	margin-bottom: 4px;
	background-color: $theme-color-3;

	&.not-scrolled {
		box-shadow: none;
		background-color: transparent;
	}

	.logo {
		width: $header-height;
		margin: 0 5px;
	}

	&__region {
		display: flex;
		align-items: center;

		&--flip {
			flex-direction: row-reverse;
		}

		&--slider-animation {
			h1 {
				transition: all .15s;
				opacity: 0;
				transform: translateX(-6%);
			}
			
			&:hover {
				h1 {
					opacity: 1;
					transform: translateX(0%);
				}
			}
		}
	}
}

.nav {
	height: 100%;

	&__item {
		display: flex;
		align-items: center;
		height: 100%;
		padding: .5rem 2rem;
	}
}

@media only screen and (max-width: $screen-tablet) {
	.header {
		.home-link {
			display: none;
		}
	}

	.nav {
		&__item {
			&--only-small {
				display: flex;
			}
		}
	}
}

@media only screen and (max-width: $screen-mobile) {
	.header {
		.home-link {
			display: none;
		}
	}

	.nav {
		&__item {
			font-size: .9rem;
			padding: 0 .4rem;
			margin: 0 .3rem;
		}
	}
}
</style>
