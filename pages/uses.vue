<template>
	<main>
		<p>
			I do computer stuff with computer.
		</p>
		<ImageThumb class="image"
			:openable="true"
			title="My computer."
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
@import "@/layouts/theme.scss";

</style>