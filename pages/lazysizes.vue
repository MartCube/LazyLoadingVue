<template>
	<div class="container">
		<div class="intro">
			<h2>Lazy loading with Vue.js</h2>
			<h1>Lazysizes</h1>
			<h3>
				<n-link exact to="/">vue custom directives</n-link>
			</h3>
		</div>

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
