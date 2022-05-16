<nav>
	<span id="left-side">
		<a href="/">Home</a>
		<a href="/blog">Blog</a>
	</span>

	<span id="right-side">
		<a href="/contact">Contact</a>
	</span>
</nav>

<style lang="scss">
	@import "../../constants.scss";

	nav {
		display: flex;
		justify-content: space-between;
		align-items: center;

		span {
			margin: 1rem;
		}

		a {
			padding: 0.5rem;
		}
	}
</style>
