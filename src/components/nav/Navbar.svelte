<script>
	import HamburgerButton from "./HamburgerButton.svelte";
</script>

<nav>
	<HamburgerButton />
	<div class="content-fit">
		<span id="left-side">
			<a href="/" id="main">Jordan Software</a>
			<a href="/blog">Blog</a>
			<a href="/projects">Projects</a>
		</span>

		<span id="right-side">
			<a href="/contact">Contact</a>
		</span>
	</div>
</nav>

<style lang="scss">
	@import "../../constants.scss";

	nav {
		background-color: rgba($color: rgb(177, 233, 233), $alpha: 1);
		$h-offset: 0px;
		$v-offset: 5px;
		$blur: 30px;
		box-shadow: rgb(177, 233, 233) $h-offset $v-offset $blur;
		-webkit-user-select: none;
		user-select: none;

		#hamburger {
			color: teal;
			font-size: 30pt;

			position: fixed;
			margin-left: $spacer1;
			margin-top: $spacer1;

			&.active {
				span {
					background-color: transparent;
				}
				&:before {
					transform: rotate(45deg);
					top: -10px;
					height: 2px;
					background: rgba(255, 255, 255, 0.5);
					width: 30px;
				}
				&:after {
					transform: rotate(-45deg);
					bottom: -10px;
					height: 2px;
					background: rgba(255, 255, 255, 0.5);
					width: 30px;
				}
			}
		}

		div {
			display: flex;
			justify-content: space-between;
			align-items: center;

			@media (max-width: 1000px) {
				flex-direction: column;
				align-items: center;
				justify-content: center;

				height: fit-content;
			}
		}

		span {
			$child-margin: $spacer1;
			$child-padding: $spacer1;
			&:first-child#left-side {
				margin-left: (-$child-margin - $child-padding);
				@media (max-width: 1000px) {
					margin: 0;
				}
			}

			&:last-child#right-side {
				margin-right: (-$child-margin - $child-padding);
				@media (max-width: 1000px) {
					margin: 0;
				}
			}
			margin: $spacer1;

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
				margin: $spacer1 / 2;
				display: inline;
				margin: 0;
			}
		}
	}
</style>
