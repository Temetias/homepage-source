<template>
	<footer class="footer">
		<div class="socials">
			<Social path="https://github.com/Temetias"
				iconClass="fa fa-github-square"
			/>
			<Social path="https://twitter.com/Temetias"
				iconClass="fa fa-twitter-square"
			/>
			<Social path="https://www.linkedin.com/in/teemu-karppinen-1174b1139"
				iconClass="fa fa-linkedin-square"
			/>
		</div>
	</footer>	
</template>

<script>
import Social from "~/components/Social.vue";

export default {
	components: {
		Social,
	},
};
</script>

<style lang="scss" scoped>
.footer {
	display: flex;
	justify-content: center;
}

.socials {
	display: flex;
}
</style>