<template>
	<div class="container">
		<div class="custom-container">
			<h1 class="custom-heading">Recent projects</h1>
			<div class="custom-card-container">
				<div
					v-for="(card, index) in cards"
					:key="index"
					class="custom-card"
					:class="{ 'slide-in': inView[index] }"
				>
					<div class="custom-card__body">
						<h3>{{ card.title }}</h3>
						<p>{{ card.description }}</p>
						<a
							v-if="isDemoLink(card.linkHref)"
							:href="card.linkHref"
							target="_blank"
							>Visit site</a
						>
						<a
							v-else-if="isGithubLink(card.linkHref)"
							:href="card.linkHref"
							target="_blank"
							>View source</a
						>
					</div>
				</div>
			</div>
			<Footer />
		</div>
	</div>
</template>

<script>
import Footer from "../components/Footer.vue";
export default {
	components: { Footer },
	data() {
		return {
			cards: [
				{
					title: "tanaruz boats",
					description:
						"This project showcases the development of a 3D-printed customizable boat constructed from reusable polymers.",
					linkHref: "https://tanaruz.boats/",
				},
				{
					title: "thuisborg",
					description:
						"ThuisBorg is a platform that enables homeowners to unlock the value of their properties by providing fair purchase prices and offering affordable rental options.",
					linkHref: "https://thuisborg.nl/",
				},
				{
					title: "Car Damage",
					description:
						"The Car-Damage Detection System is a software application that allows users to view and assess existing damages on each side of a vehicle. The system leverages computer vision and image processing techniques.",
					linkHref: "https://github.com/titotarek/Car_Damge_Assessment_App",
				},
				{
					title: "DTT Real State",
					description:
						"create a web application for house listings, which allows the user toview a list of houses that are currently available for sale, and create, edit and delete theirown listings",
					linkHref: "https://github.com/titotarek/DTT-REAL-STATE",
				},
				{
					title: "Eagle Eye NetWork",
					description:
						"Api is to Authenticate the user to view the cameras from authentication verification by refresh_token",
					linkHref: "https://github.com/titotarek/eagle-eye-newWork",
				},
				{
					title: "Marvel  Movie ",
					description:
						"This is a full-stack project that allows you to get, create, update, and delete movie posts related to Marvel movies",
					linkHref: "https://github.com/titotarek/MVEN_Marvel_Movie",
				},
				{
					title: " Q&A (Question & Answer) ",
					description:
						"This powerful combination of technologies allows for seamless interaction and efficient data management, providing an excellent user experience",
					linkHref: "https://github.com/titotarek/backend-frontend",
				},

				{
					title: "Authentication Project",
					description:
						"this project demonstrates how to implement authentication login functionality, protected routes, and logout functionality",
					linkHref: "https://github.com/titotarek/authentication",
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
			const scrollTop =
				window.pageYOffset || document.documentElement.scrollTop;
			const cards = this.$el.getElementsByClassName("custom-card");

			for (let i = 0; i < cards.length; i++) {
				const cardRect = cards[i].getBoundingClientRect();
				const isVisible = cardRect.top < windowHeight && cardRect.bottom >= 0;

				this.inView[i] = isVisible;
			}

			if (scrollTop === 0) {
				this.inView[0] = true;
			}
		},
		isDemoLink(linkHref) {
			return (
				linkHref.startsWith("https://") && !linkHref.includes("github.com")
			);
		},
		isGithubLink(linkHref) {
			return linkHref.startsWith("https://github.com");
		},
	},
};
</script>
