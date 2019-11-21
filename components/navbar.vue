<template>
	<nav class="navbar ">
		<div class="links" :class="{ active: isActive }" @click="CloseMenu">
			<n-link exact to="/">Vue Custom Directives</n-link>
			<n-link to="/lazysizes">Lazysizes package</n-link>
			<n-link to="/nolazyload">Without lazy loading</n-link>
		</div>

		<div class="button" :class="{ active: isActive }" @click="ShowHideMenu">
			<span class="top" />
			<span class="middle" />
			<span class="bottom" />
		</div>
	</nav>
</template>

<script>
export default {
	data() {
		return {
			isActive: false,
		}
	},
	methods: {
		ShowHideMenu() {
			this.isActive = !this.isActive
		},
		CloseMenu() {
			this.isActive = false
		},
	},
}
</script>

<style lang="scss" scooped>
.navbar {
	position: fixed;
	top: 0;
	z-index: 999;
	height: 50px;
	width: 100%;
	background: white;

	display: flex;
	justify-content: flex-end;
	align-items: center;
	align-content: center;
	.links {
		display: flex;
		flex-direction: row;
		justify-content: space-around;
		align-content: space-around;
		flex-basis: 100%;

		a {
			text-decoration: none;
			font-size: 1.2em;
			text-transform: uppercase;
			color: #34495e;
			outline: none;

			&::after {
				content: '';
				display: block;
				width: 100%;
				height: 4px;
				border-radius: 10px;
				background: #41b883;

				opacity: 0;
				transition: all 0.3s;
				transform: translateY(10px);
			}

			&:hover::after {
				opacity: 1;
				transform: translateY(5px);
			}

			&.nuxt-link-active::after {
				opacity: 1;
				transform: translateY(5px);
			}
		}

		&.active {
			display: flex;
			flex-direction: column;
			align-content: center;
			align-items: center;

			padding: 10% 0;
			background-color: rgba(52, 73, 94, 0.9);

			position: fixed;
			top: 0;
			right: 0;
			width: 100%;
			height: 100vh;

			a {
				animation: fadeInRight 0.5s ease forwards;
				color: white;
				&::after {
					background: #41b883;
				}
			}
		}
	}

	.logo {
		display: flex;
		flex-basis: 50%;
		padding-left: 20px;
		color: white;
		img {
			height: 50px;
		}
	}

	.button {
		display: none;
		position: fixed;
		top: 0;
		right: 0;
		margin: 15px;
		height: 27px;
		width: 35px;
		cursor: pointer;

		transition: all 0.3s ease;
		&.active {
			.top {
				transform: translateY(11px) translateX(0) rotate(45deg);
				background: white;
			}
			.middle {
				opacity: 0;
			}

			.bottom {
				transform: translateY(-11px) translateX(0) rotate(-45deg);
				background: white;
			}
		}

		span {
			background: #34495e;
			border-radius: 10px;
			height: 5px;
			width: 100%;
			position: absolute;
			top: 0;
			transition: all 0.3s ease;

			&:nth-of-type(2) {
				top: 11px;
				width: 80%;
				right: 0;
			}

			&:nth-of-type(3) {
				top: 22px;
			}
		}
	}
}

@keyframes fadeInRight {
	0% {
		opacity: 0;
		transform: translateX(50px);
	}
	100% {
		opacity: 1;
		transform: translateX(0px);
	}
}

@media (max-width: 750px) {
	.navbar {
		justify-content: flex-start;
		align-items: center;
		align-content: center;
		.logo {
			flex: none;
		}
		.links {
			display: none;
		}
		.button {
			display: flex;
		}
	}
}
</style>
