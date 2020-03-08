<template>
	<main>
		<p>
			I like climbing and stuff.
		</p>
		<ImageThumb class="image"
			title="Me climbing."
			src="/test-image.jpg"
			thumbSrc="/test-image.jpg"
			alt="test-image.jpg"
		/>
	</main>
</template>

<script>
import ImageThumb from "~/components/ImageThumb.vue";

export default {
	head() {
		return {
			title: "Teemu Karppinen /about"
		};
	},
	components: {
		ImageThumb,
	},
};
</script>

<style lang="scss">

</style>
