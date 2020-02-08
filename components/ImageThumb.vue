<template>
	<div class="image">
		<img class="image__displayer"
			:class="{ 'image__displayer--openable': openable }"
			@click="handleClick"
			:src="src"
			:alt="alt"
			:title="title"
		/>
		<ImageModal
			v-if="showModal"
			@close="() => showModal = false"
			:src="src"
			:alt="alt"
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
		"openable",
		"src",
		"alt",
		"title",
	],
	methods: {
		handleClick() {
			if (this.openable) {
				this.showModal = true;
			}
		}
	},
};
</script>

<style lang="scss" scoped>
.image {
	&__displayer {
		width: 100%;

		&--openable {
			cursor: pointer;
		}
	}
}
</style>