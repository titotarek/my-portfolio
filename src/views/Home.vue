<template>
	<div class="home">
		<AboutMe />
		<Slider />
		<ContentText />
		<Cards />
		<ContentMe />
		<Footer />
	</div>
</template>

<script>
import AboutMe from "../components/AboutMe.vue";
import Cards from "../components/Cards.vue";
import ContentMe from "../components/ContentMe.vue";
import Footer from "../components/Footer.vue";
import Slider from "../components/Slider.vue";
import ContentText from "../components/ContentText.vue";

export default {
	components: { AboutMe, Slider, Cards, ContentMe, Footer,ContentText},
	name: "Home",
};
</script>
