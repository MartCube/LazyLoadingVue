<template>
	<div class="container">
		<ImageItem2 :source="images[0]" />
		<ImageItem2 :source="images[1]" />
		<ImageItem2 :source="images[2]" />
		<ImageItem2 :source="images[3]" />
	</div>
</template>

<script>
import ImageItem2 from '~/components/ImageItem2.vue'

export default {
	components: {
		ImageItem2,
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
