
<template>
	<div class="container">
		<header>
			<div class="logo">
				<img src="../assets/image/art.png" />
			</div>
			<nav>
				<ul class="nav-links" :class="{ 'nav-active': isOpen }">
					<li>
						<router-link
							:to="{ path: '/' }"
							:class="{ active: currentRoute === '/' }"
							@click="closeNav"
							>Home</router-link
						>
					</li>
					<li>
						<router-link
							:to="{ path: '/about' }"
							:class="{ active: currentRoute === '/about' }"
							@click="closeNav"
							>About</router-link
						>
					</li>
					<li>
						<router-link
							:to="{ path: '/my-work' }"
							:class="{ active: currentRoute === '/my-work' }"
							@click="closeNav"
							>Work</router-link
						>
					</li>
				</ul>
				<div class="burger" @click="toggleNav">
					<div class="line1"></div>
					<div class="line2"></div>
					<div class="line3"></div>
				</div>
			</nav>
		</header>
	</div>
</template>

<script>
export default {
	data() {
		return {
			isOpen: false,
			currentRoute: "",
		};
	},

	methods: {
		toggleNav() {
			this.isOpen = !this.isOpen;
			this.isLinkSelected = false;
		},
		closeNav() {
			this.isOpen = false;
			this.isLinkSelected = false;
		},
	},

	watch: {
		$route(to) {
			this.currentRoute = to.path;
		},
	},
};
</script>
