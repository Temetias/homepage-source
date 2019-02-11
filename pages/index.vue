<template>
	<div class="main">
		<section>
			<h1>Who is dis?</h1>
			<p>
				2 Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet.
				2 Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet
			</p>
			<p>
				2 Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet.
				2 Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet
			</p>
			<p>
				2 Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet.
				2 Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet
			</p>
		</section>
		<section>
			<h1>My projects</h1>
			<p>
				2 Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet.
				2 Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet
			</p>
			<GithubRepo 
				v-for="(repo, index) in githubRepos"
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
	mounted() {
		fetch("https://api.github.com/users/Temetias/repos")
			.then(response => response.json())
				.catch(error => console.error(error))
			.then(response => this.githubRepos = response)
				.catch(error => console.error(error))
	}
}
</script>

<style lang="scss" scoped>
@import "@/layouts/theme.scss";

.main {
	color: $theme-darkgray;
	width: 100vw;
	padding: 2rem;
}

section {
	padding: 5vh 0;

	p {
		padding: 2vh 0;
	}
}

</style>
