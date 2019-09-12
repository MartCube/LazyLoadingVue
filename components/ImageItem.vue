<template>
	<figure v-lazyload class="image_wrapper">
		<img class="image" :data-url="source" alt="image" />
		<img class="placeholder" :src="placeholder" alt="placeholder" />
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
		placeholder: {
			type: String,
			required: true,
		},
	},
}
</script>

<style lang="scss" scoped>
.image_wrapper {
	margin: 10%;

	display: flex;
	justify-content: center;
	align-items: center;
	align-content: center;

	.placeholder {
		position: relative;
		width: 80vw;
		-webkit-filter: blur(10px);
		filter: blur(10px);
		transition: opacity 0.5s linear;
	}

	.image {
		position: absolute;
		width: 80vw;

		opacity: 0;
		transition: opacity 1s linear;
	}

	&.loaded {
		.placeholder {
			opacity: 0;
		}
		.image {
			opacity: 1;
		}
	}
}
</style>
