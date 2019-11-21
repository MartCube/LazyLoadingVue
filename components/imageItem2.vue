<template>
	<figure class="image_wrapper">
		<img class="image lazyload blur-up" :data-srcset="source" :src="placeholder" />
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
	min-height: 100vh;

	display: flex;
	justify-content: center;
	align-items: center;
	align-content: center;
	.image {
		width: 80vw;
	}

	.blur-up {
		-webkit-filter: blur(5px);
		filter: blur(5px);
		transition: filter 3000ms 500ms, -webkit-filter 3000ms 500ms;
	}
	.blur-up.lazyloaded {
		-webkit-filter: blur(0);
		filter: blur(0);
	}
}
</style>
