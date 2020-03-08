<template>
	<div class="image">
		<img class="image__displayer"
			@click="() => this.showModal = true"
			:src="thumbSrc"
			:alt="title"
			:title="title"
		/>
		<ImageModal
			v-if="showModal"
			@close="() => showModal = false"
			:src="src"
			:alt="title"
			:title="title"
		/>
	</div>
</template>

<script>
import ImageModal from "~/components/ImageModal.vue";

export default {
	data() {
		return {
			showModal: false,
		};
	},
	components: {
		ImageModal,
	},
	props: [
		"thumbSrc",
		"src",
		"title",
	],
};
</script>

<style lang="scss">
.image {
	&__displayer {
		width: 100%;
		cursor: pointer;
	}
}
</style>
