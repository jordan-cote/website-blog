<div class="content-fit nav-content">
	<span id="left-side">
		<a href="/" id="main">Jordan Software</a>
		<a href="/blog">Blog</a>
		<a href="/projects">Projects</a>
	</span>

	<span id="right-side">
		<a href="/contact">Contact</a>
	</span>
</div>

<style lang="scss">
	@import "../../constants.scss";
	.nav-content {
		display: flex;
		justify-content: space-between;
		align-items: center;

		@media (max-width: 1000px) {
			flex-direction: column;
			align-items: flex-end;
			justify-content: center;

			background-color: lightgray;
			z-index: 10;
			position: fixed;
			width: min(50%, 200px);
			right: 0;
			padding: 0;
			margin: 0 0 0 0;
			list-style-type: none;
			-webkit-font-smoothing: antialiased;
			/* to stop flickering of text in safari */
			top: 0%;
			transform-origin: 0% 0%;
			transform: translateY(-100%);

			transition: transform 0.5s cubic-bezier(0.77, 0.2, 0.05, 1);
		}
	}

	span {
		$child-margin: $spacer1;
		$child-padding: $spacer1;
		margin: $spacer1;
		&:first-child#left-side {
			margin-left: (-$child-margin - $child-padding);
			@media (max-width: 1000px) {
				margin: 0;
				align-items: flex-end;
			}
		}

		&:last-child#right-side {
			margin-right: (-$child-margin - $child-padding);
			@media (max-width: 1000px) {
				margin: 0;
				align-items: flex-end;
			}
		}

		@media (max-width: 1000px) {
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
		}
	}

	a {
		@include margin-x($spacer1);
		padding: 0.5rem;
		@include padding-y($spacer1);
		text-decoration: none;
		font-size: 20px;

		color: rgb(0, 24, 18);
		font-weight: bold;

		&::before {
			content: "| ";
		}
		&::after {
			content: " |";
		}

		&:hover {
			color: teal;
		}

		@media (max-width: 1000px) {
			margin: calc($spacer1 / 2);
			display: inline;
			margin: 0;
		}
	}
</style>
