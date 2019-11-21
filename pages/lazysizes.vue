<template>
	<div class="container">
		<ImageLazysize :source="images[0]" :placeholder="placeholder[0]" />
		<ImageLazysize :source="images[1]" :placeholder="placeholder[1]" />
		<ImageLazysize :source="images[2]" :placeholder="placeholder[2]" />
		<ImageLazysize :source="images[3]" :placeholder="placeholder[3]" />
	</div>
</template>

<script>
import ImageLazysize from '~/components/ImageLazysize.vue'

export default {
	components: {
		ImageLazysize,
	},
	data() {
		return {
			images: ['images/1.jpg', 'images/2.jpg', 'images/3.jpg', 'images/4.jpg'],
			placeholder: ['placeholder/1.jpg', 'placeholder/2.jpg', 'placeholder/3.jpg', 'placeholder/4.jpg'],
		}
	},
}
</script>

<style lang="scss" scoped></style>
