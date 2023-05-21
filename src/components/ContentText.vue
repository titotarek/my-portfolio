<template>
	<div class="container">
		<p class="animate-slide" ref="paragraph">
			It all begins with an idea. Maybe you want to launch a business.<br />
			Maybe you want to turn a hobby into something more.<br />
			Don't worry about sounding professional. Sound like you.<br />
			There are over 1.5 billion websites out there,<br />
			but your story is what's going to separate this one from the rest.<br />
			I'm very excited to have you here.<br />
			Feel free to reach out to me with any project ideas you have, <br />or
			just to say hello. I'm always happy to help!
		</p>
	</div>
</template>

<script>
export default {
	mounted() {
		window.addEventListener("scroll", this.animateElement);
	},
	unmounted() {
		window.removeEventListener("scroll", this.animateElement);
	},
	methods: {
		animateElement() {
			const element = this.$refs.paragraph;
			const elementPosition = element.getBoundingClientRect().left;
			const screenPosition = window.innerHeight / 1.2;

			if (elementPosition < screenPosition) {
				element.classList.add("animate");
			} else {
				element.classList.remove("animate");
			}
		},
	},
};
</script>
