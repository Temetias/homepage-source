<template>
	<main class="projects">
		<header>
			Here you can find some highlights of my personal projects. Large part of my freetime coding goes
			into learning new stuff, or working on private projects so this list isn't anything spectacular.
			<br><br>
			There are still some worth showing so go ahead and check them out!
		</header>
		<section class="async-section">
			<Loader class="async-section__loader"
				v-if="!projects.length"
			/>
			<Box v-for="project in projects"
				:key="project.name">
				<div class="project">
					<h3 :id="project.name">{{ project.name }}</h3>
					<p>{{ project.info }}</p>
					<div class="project__footer">
						<a :href="'https://github.com/Temetias/' + project.name">Github</a>
						<a v-for="link in project.links"
							:key="link.title"
							:href="link.href">
							{{ link.title }}
						</a>
					</div>
				</div>
			</Box>
		</section>
	</main>
</template>

<script>
import Box from "~/components/Box.vue";
import Loader from "~/components/Loader.vue";

export default {
	components: {
		Box,
		Loader,
	},
	data() {
		return {
			projects: [],
		};
	},
	created() {
		fetch("https://api.github.com/users/Temetias/repos")
			.then(response => response.json())
				.catch(console.error)
				.then(repos => {
					repos.forEach(({ name }) => {
						fetch(`https://raw.githubusercontent.com/Temetias/${name}/master/project-info.txt`)
							.catch(() => {})
							.then(res => res.text())
							.then(rawInfo => {
								if (rawInfo.indexOf("404: Not Found") === -1) {
									const info = rawInfo.split("#link#")[0];
									this.projects.push({ name, info, links: [ JSON.parse(rawInfo.split("#link#")[1]) ] });
								}
							});
					});
				});
	},
};
</script>

<style lang="scss">
@import "@/layouts/theme.scss";

.projects header {
	padding: 10rem 0;
	font-size: 1.5rem;
}

@media only screen and (max-width: $screen-mobile) {
	.projects header {
		padding: 0 0 5rem 0;
		font-size: 1.3rem;
	}
}

.async-section {
	&__loader {
		min-height: 100vh;
	}
}
</style>