<template>
	<header class="header"
		:class="{ 'not-scrolled': scrollTrigger }">
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
			<nuxt-link class="nav__item nav__item--only-small no-outline"
				to="/">
				Home
			</nuxt-link>
			<nuxt-link class="nav__item no-outline"
				to="/about">
				About
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
	data() {
		return {
			lastScroll: 0,
			scrollingDown: false,
		};
	},
	mounted() {
		document.getElementById("main-content").onscroll = ({ target }) => {
			this.scrollingDown = this.lastScroll < target.scrollTop;
			this.lastScroll = target.scrollTop;
		};
	},
	computed: {
		scrollTrigger() {
			return window.innerHeight / 3 > this.lastScroll;
		}
	}
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
	color: $theme-color-alt;
	transition: background-color .1s;

	&.not-scrolled {
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

		&--only-small {
			display: none;
		}
	}
}

@media only screen and (max-width: 640px) {
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

@media only screen and (max-width: 475px) {
	.header {
		flex-direction: column;
		height: auto;

		&__region {
			width: 100%;
			background-color: $theme-bg-color-alt;
			z-index: 10;

			&--small-screen-left {
				z-index: 20;
				flex-direction: row;
			}
		}

		.home-link {
			display: none;
		}
	}

	.nav {
		position: fixed;
		top: $header-height;
		height: 2rem;
		justify-content: center;
		transition: transform .2s;

		* {
			transition: opacity .15s;
			opacity: 1;
		}

		&.scrolling-down {
			transform: translateY(-100%);
			
			* {
				opacity: 0;
			}
		}
	}
}
</style>
