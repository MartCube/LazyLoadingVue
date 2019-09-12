<template>
	<div class="container">
		<div class="image_wrapper">
			<img src="/images/1.jpg" alt="" />
			<img src="/images/2.jpg" alt="" />
			<img src="/images/3.jpg" alt="" />
			<img src="/images/4.jpg" alt="" />
		</div>
	</div>
</template>

<style lang="scss" scoped>
.image_wrapper {

	//position: relative;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	align-content: center;



	img {
		margin: 10%;
		width: 80vw;

		opacity: 1;
		transition: opacity 1s linear;
	}


}
</style>

</style>
