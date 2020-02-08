<template>
	<div class="main">
		<section>
			<h1>About me</h1>
			<p>
				My name is Teemu Karppinen and I'm a Full Stack Developer from Joensuu, Finland.
				I've been working in software development for 
				{{ new Date().getFullYear() - 2018 }} 
				year{{ new Date().getFullYear() - 2018 > 1 ? "s" : "" }} and studied in University
				of Eastern Finland for 3 years. I'm also continuously learning and trying new 
				technologies from online resources.
			</p>
			<p>
				My current title is Software Developer. My work consists of full 
				stack development of web-based industrial IOT-solutions. Even though I do full 
				stack, I consider my area of expertise to be front end development with 
				front end frameworks.
			</p>
			<p>
				My professonial experience consists mostly of TypeScript, JavaScript, Vue.js, 
				CSS, SASS, HTML5, PHP and Drupal. I've also touched several other technologies 
				and tools along the way. In my personal projects I've also used Python, Java, 
				React, Gatsby and pretty much every single Vue.js tool I've found.   
			</p>
		</section>
		<section>
			<h1>My projects</h1>
			<p>
				For the sake of content, here's a list of my current public Github repositories, 
				including the source code for this page. You'll propably find that none of them 
				are finished. The main goal of my hobby coding is to try out new things and gain experience about different 
				technologies. Regardless, feel free to fork them and try them out!
			</p>
			<GithubRepo class="github-repo"
				v-for="(repo, index) in filteredAndSortedGithubRepos"
				:key="index"
				:index="index"
				:repo="repo"
			/>
		</section>
	</div>
</template>

<script>
import GithubRepo from "~/components/GithubRepo"

export default {
	components: {
		GithubRepo
	},
	data() {
		return {
			githubRepos: []
		}
	},
	computed: {
		filteredAndSortedGithubRepos() {
			const filtered = this.githubRepos.filter(repo => {
				return repo.name.toLowerCase() !== "temetias.github.io"
			})
			const sorted = filtered.sort((a, b) => {
				return new Date(b.pushed_at) - new Date(a.pushed_at)
			})
			return filtered
		}
	},
	mounted() {
		fetch("https://api.github.com/users/Temetias/repos")
			.then(response => response.json())
				.catch(error => console.error(error))
			.then(response => this.githubRepos = response)
				.catch(error => console.error(error))
	},
	head() {
		return {
			title: "Teemu Karppinen"
		}
	}
}
</script>

<style lang="scss" scoped>
@import "@/layouts/theme.scss";

.main {
	color: $theme-darkgray;
	width: 100vw;
	padding: 2rem 5vw;
}

section {
	padding: 5vh 0;

	h1 {
		color: $theme-dark-red;
		font-size: 3.5rem;
	}

	p {
		padding: 2vh 0;
		font-size: 1.25rem;
	}

	.github-repo {
		border-top: 1px solid $theme-red;
		
		&:nth-child(3) {
			border: none;
		}
	}
}

</style>
