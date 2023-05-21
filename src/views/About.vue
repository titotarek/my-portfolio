<template>
	<div class="container">
		<div class="about-section">
			<div class="about-image">
				<img src="../assets/image/Tarek.jpg" alt="Image 1" />
			</div>
			<div class="about-text">
				<h1 class="section-heading">About Me</h1>
				<h2 class="sub-heading">Hello there 👋, I’m Tarek.</h2>
				<p>
					As a Front-End and Full-Stack Developer, I have experience with a wide
					range of web development technologies, including Node.JS, ReactJS,
					Vue.JS, and more. I've been involved with company/team sizes that use
					AGILE/SCRUM methodologies to deliver high quality software projects on
					time and within budget.
				</p>
				<p>
					In addition to my technical skills, I have a strong attention to
					detail and a passion for creating intuitive and responsive user
					interfaces. I take pride in writing clean, maintainable, and scalable
					code that is easily understood and modified by other developers.
				</p>

				<p>
					I am comfortable working both independently and collaboratively, and
					have excellent communication skills that allow me to work effectively
					with stakeholders, designers, and other developers. Whether it's
					building a brand new application from scratch or adding new features
					to an existing one, I am always eager to take on new challenges and
					push the boundaries of what's possible.
				</p>

				<p>
					If you'd like to view my resume, please click on this link:
					<a :href="pdfUrl" download>
						<button>View Resume</button>
					</a>
				</p>
			</div>
		</div>
		<Footer />
	</div>
</template>

<script>
import Footer from "../components/Footer.vue";

export default {
	components: { Footer },
	data() {
		return {
			pdfUrl: "/pdf/Resume-Tarek-Abdalla.pdf",
		};
	},
};
</script>

