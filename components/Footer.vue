<template>
	<footer class="footer">
		<div class="socials">
			<Social class="socials__icon"
				path="https://github.com/Temetias"
				iconClass="fa fa-github-square"
				title="Temetias - Github"
			/>
			<Social class="socials__icon"
				path="https://twitter.com/Temetias"
				iconClass="fa fa-twitter-square"
				title="Temetias - Twitter"
			/>
			<Social class="socials__icon"
				path="https://www.linkedin.com/in/teemu-karppinen-1174b1139"
				iconClass="fa fa-linkedin-square"
				title="Teemu Karppinen - LinkedIn"
			/>
			<Social class="socials__icon"
				path="https://www.instagram.com/zoomtimmy/"
				iconClass="fa fa-instagram"
				title="zoomtimmy - Instagram"
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

	&__icon {
		font-size: 2rem;
		margin: .3rem;
	}
}
</style>