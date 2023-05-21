<template>
	<div class="container">
		<footer class="footer">
			<div class="footer__left">
				<p>© {{ currentYear }} All rights reserved.</p>
			</div>
			<div class="footer__right">
				<a
					v-for="(link, index) in links"
					:key="link.id"
					:href="link.url"
					class="footer__link"
				>
					{{ link.text }}
					<span v-if="shouldShowSeparator(index)" class="footer__separator"
						>/</span
					>
				</a>
			</div>
		</footer>
	</div>
</template>

<script>
export default {
	data() {
		return {
			links: [
				{
					id: 1,
					text: "Linkedin",
					url: "https://www.linkedin.com/in/tarek-abdalla-371863207/",
				},
				{
					id: 2,
					text: "GitHup",
					url: "https://github.com/titotarek?tab=repositories",
				},
			],
			currentYear: new Date().getFullYear(),
		};
	},
	methods: {
		shouldShowSeparator(index) {
			return index !== this.links.length - 1;
		},
		updateYear() {
			this.currentYear = new Date().getFullYear();
		},
	},
	mounted() {
		setInterval(this.updateYear, 1000);
	},
};
</script>

