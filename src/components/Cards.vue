
<template>
	<div class="container">
		<div class="card-container">
			<div
				class="card"
				v-for="(card, index) in cards"
				:key="index"
				:class="{ 'slide-in': inView[index] }"
			>
				<div class="card__body">
					<img class="card-image" :src="card.image" alt="" />
					<h1 class="card-heading">{{ card.heading }}</h1>
					<p class="card-paragraph">{{ card.paragraph }}</p>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			cards: [
				{
					image: require("../assets/image/ux-design.png"),
					heading: "UX & UI",
					paragraph:
						"Designing interfaces that are intuitive, efficient, and enjoyable to use.",
				},
				{
					image: require("../assets/image/prototype.png"),
					heading: "Web & Mobile App",
					paragraph:
						"Transforming ideas into exceptional web and mobile app experiences.",
				},
				{
					image: require("../assets/image/app-development (1).png"),
					heading: "Design & Creative",
					paragraph:
						"Crafting visually stunning designs that connect with your audience",
				},
				{
					image: require("../assets/image/app-development.png"),
					heading: "Development",
					paragraph:
						"Bringing your vision to life with the latest technology and design trends.",
				},
			],
			inView: [], // Array to track visibility of cards
		};
	},
	mounted() {
		window.addEventListener("scroll", this.handleScroll);
		this.handleScroll();
	},
	beforeUnmount() {
		window.removeEventListener("scroll", this.handleScroll);
	},
	methods: {
		handleScroll() {
			const windowHeight = window.innerHeight;
			const cards = this.$el.getElementsByClassName("card");

			for (let i = 0; i < cards.length; i++) {
				const cardRect = cards[i].getBoundingClientRect();
				const isVisible = cardRect.top < windowHeight;

				this.inView[i] = isVisible;
			}
		},
	},
};
</script>

<style>

</style>
