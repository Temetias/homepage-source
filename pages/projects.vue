<template>
	<main>
		<header>

		</header>
		<section class="async-section">
			<Loader v-if="!projects.length"/>
			<Box v-for="project in projects"
				:key="project.name">
				<div class="project">
					<h3>{{ project.name }}</h3>
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
	mounted() {
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
									console.log(rawInfo.split("#link#")[1])
									this.projects.push({ name, info, links: [ JSON.parse(rawInfo.split("#link#")[1]) ] });
								}
							});
					});
				});
	},
};
</script>