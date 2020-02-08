<template>
	<div id="layout">
		<section id="menu">
			<SocialMedias/>
		</section>
		<Header id="header"/>
		<nuxt id="content" />
	</div>
</template>

<script>
import SocialMedias from "~/components/SocialMedias.vue"
import Header from "~/components/Header.vue"

export default {
	components: {
		SocialMedias,
		Header
	}
}
</script>


<style lang="scss" scoped>
@import "@/layouts/theme.scss";

#layout {
	display: flex;
	flex-direction: row;
}

#menu {
	position: fixed;
	display: flex;
	flex-direction: column;
	justify-content: flex-end;
	height: 100vh;
	width: 60px;
	padding: 5px;
	background-color: $theme-dark-red;
	box-shadow: $theme-shadow;
	@media only screen and (max-width: $break-small) {
		width: 100vw;
		height: 50px;
	}
	z-index: 1;
}

#content {
	margin-top: 100vh;
	margin-left: 60px;
	@media only screen and (max-width: $break-small) {
		margin-left: 0;
	}
}

#header {
	position: absolute;
	top: 0;
	left: 0;
	z-index: 2;
}
</style>
