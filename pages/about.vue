<template>
	<main>
		<p>
			I like climbing and stuff.
		</p>
		<ImageThumb class="image"
			:openable="true"
			title="Me climbing."
			src="/test-image.jpg"
			alt="test-image.jpg"
		/>
	</main>
</template>

<script>
import ImageThumb from "~/components/ImageThumb.vue";

export default {
	components: {
		ImageThumb,
	},
};
</script>

<style lang="scss">
.image {
	width: 30vw;
}
</style>