<template>
	<div class="social">
		<a class="no-underline"
			:href="path">
			<i :class="iconClass"></i>
		</a>
	</div>
</template>

<script>
export default {
	props: [
		"path",
		"iconClass",
	],
};
</script>

<style lang="scss">
.social {
	i {
		cursor: pointer;
	}
}
</style>