<template>
	<div>
		<Header />
	</div>
	<router-view />
</template>

<script>
import Header from "./components/Header.vue";
export default {
	components: { Header },
};
</script>
<style>
@import "./assets/styles/header.css";
@import "./assets/styles/global-ruls";
@import "./assets/styles/about-me.css";
@import "./assets/styles/slider.css";
@import "./assets/styles/content-me.css";
@import "./assets/styles/cards.css";
@import "./assets/styles/content-text.css";
@import "./assets/styles/work-card.css";
@import "./assets/styles/footer.css";
@import "./assets/styles/about.css";
</style>
