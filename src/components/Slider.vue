<template>
	<div>
		<div class="image-slider">
			<div class="slider">
				<div
					class="slides"
					:style="{ transform: 'translateX(' + translateX + 'px)' }"
				>
					<div
						class="slide"
						v-for="(image, index) in imagesWithDuplicates"
						:key="index"
					>
						<img :src="image.src" alt="image.alt" />
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	// name: "Slider",
	data() {
		return {
			images: [
				{ src: require("../assets/image/html-file.png") },
				{ src: require("../assets/image/css.png") },
				{ src: require("../assets/image/js-format.png") },
				{ src: require("../assets/image/atom.png") },
				{ src: require("../assets/image/node-js.png") },
				{ src: require("../assets/image/Vue-js.png") },
			],
			currentIndex: 0,
			slideWidth: 200,
			intervalId: null,
			intervalTime: 2000,
		};
	},
	computed: {
		translateX() {
			return -(this.slideWidth * this.currentIndex);
		},
		imagesWithDuplicates() {
			// Triple the number of images to create the illusion of an infinite loop
			return [...this.images, ...this.images, ...this.images];
		},
	},
	mounted() {
		this.startSlide();
	},
	methods: {
		startSlide() {
			this.intervalId = setInterval(() => {
				this.currentIndex = (this.currentIndex + 1) % this.images.length;
			}, this.intervalTime);
		},
	},
	beforeUnmount() {
		clearInterval(this.intervalId);
	},
};
</script>
