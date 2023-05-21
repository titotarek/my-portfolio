<template>
	<div class="container">
		<div class="contact-us slide-from-left" ref="contactSection">
			<h2>Available for new challenges</h2>
			<button @click="sendEmail">
				<img src="../assets/image/mail.png" alt="Email Icon" />
				<span> Hire Me</span>
			</button>
		</div>
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
			const contactSection = this.$refs.contactSection;
			const sectionTop = contactSection.getBoundingClientRect().left;
			const windowHeight = window.innerHeight;

			if (sectionTop < windowHeight) {
				contactSection.classList.add("slide-in");
			} else {
				contactSection.classList.remove("slide-in");
			}
		},
		sendEmail() {
			window.location.href = "mailto:tarek.abdalla95@icloud.com";
		},
	},
};
</script>
