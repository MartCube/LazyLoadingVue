<template>
	<figure v-lazyload class="image_wrapper">
		<img class="image" :data-url="source" alt="image" />
	</figure>
</template>

<script>
export default {
	name: 'ImageItem',
	props: {
		source: {
			type: String,
			required: true,
		},
	},
}
</script>

<style lang="scss" scoped>
.image_wrapper {
	margin: 10%;

	.image {
		opacity: 0;
		width: 100%;
		transition: opacity 1s linear;
	}

	&.loaded {
		.image {
			opacity: 1;
		}
	}
}
</style>
