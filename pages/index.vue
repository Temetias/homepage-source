<template>
	<main>
		<header class="landing-header">
			<Logo class="logo"/>
			<div class="landing-header__text-wrapper">
				<h2>Hi, I'm Teemu Karppinen.</h2>
				<h2>I'm a full stack web developer.</h2>
			</div>
		</header>
		<section>
			<p>
				My name is Teemu Karppinen and I'm a full stack developer from Joensuu, Finland.
				I'm passionate about the software industry and creating amazing stuff with code. I'm mainly a web developer,
				but also take interest in other kinds of development as well.
			</p>
			<p>
				Currently, my title is Lead Developer in a company creating web-based industrial IOT-platforms.
				My main skills professionally are <a href="https://www.typescriptlang.org/">TypeScript</a>,
				<a href="https://www.javascript.com/">JavaScript</a>, <a href="https://vuejs.org/">Vue.js</a>,
				<a href="https://nodejs.org/en/">Node.js</a>, <a href="https://eev.ee/blog/2012/04/09/php-a-fractal-of-bad-design/">PHP</a>
				and <a href="https://sass-lang.com/">SASS</a>. On my spare time I dabble into <a href="https://www.haskell.org/">Haskell</a>.
			</p>
			<p>
				I'm enthusiastic about building and exploring solutions that are clean, maintainable and state-of-the-art
				pieces of software. I belive in using the right tools for the job and not half-assing tasks. My biggest fear is getting
				stuck with "a comfortable but outdated way of doing things" instead of being ready to go out of my comfort zone. Therefore, I
				continuosly take effort of staying in touch with the latest things in the industry.
			</p>
			<p>
				I can also manage myself in the business side of things, and have experience about working in the pre-project phase
				even with big companies, internationally. I'd go even as far to say I'm comfortable working in close synergy with the sales,
				and possibly be the translator between the dev-team and the client.
			</p>
		</section>
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

.landing-header {
	display: flex;
	justify-content: space-evenly;
	align-items: center;
	width: 100%;
	height: 100vh;

	& > * {
		max-width: 30vw;
	}

	h2 {
		font-size: 2.2rem;
	}

	.logo {
		width: 50vw;
	}
}
</style>
