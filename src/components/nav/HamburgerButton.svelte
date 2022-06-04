<!-- source: https://codepen.io/erikterwan/pen/EVzeRP -- always been my fac CSS-only implementation -->

<div id="hamburger">
	<input type="checkbox" />
	<span />
	<span />
	<span />

	<slot name="test" />
</div>

<style lang="scss">
	@import "../../constants.scss";

	@media (min-width: 1000px) {
		#hamburger {
			display: none;
		}
	}

	@media (max-width: 1000px) {
		div {
			position: fixed;
			color: teal;

			margin-top: $spacer1;
			margin-left: $spacer1;
			font-weight: bold;

			span {
				display: block;
				width: 33px;
				height: 4px;
				margin-bottom: 5px;
				position: relative;

				background: white;
				border-radius: 3px;

				z-index: 1;

				transform-origin: 4px 0px;

				transition: transform 0.5s cubic-bezier(0.77, 0.2, 0.05, 1), background 0.5s cubic-bezier(0.77, 0.2, 0.05, 1),
					opacity 0.55s ease;

				&:first-child {
					transform-origin: 0% 0%;
				}
				&:nth-last-child(2) {
					transform-origin: 0% 100%;
				}
			}

			input {
				display: block;
				width: 40px;
				height: 32px;
				position: absolute;
				top: -7px;
				left: -5px;

				cursor: pointer;

				opacity: 0; /* hide this */
				z-index: 2; /* and place it over the hamburger */

				-webkit-touch-callout: none;

				&:checked {
					& ~ span {
						opacity: 1;
						transform: rotate(45deg) translate(-2px, -1px);
						background: white;
					}

					& ~ span:nth-last-child(3) {
						opacity: 0;
						transform: rotate(0deg) scale(0.2, 0.2);
					}

					& ~ span:nth-last-child(2) {
						transform: rotate(-45deg) translate(0, -1px);
					}

					& ~ :global(.nav-content) {
						transform: none;
					}
				}
			}

			&::after {
				content: "Jordan Software";
				font-size: 16pt;
				position: absolute;
				height: 50px;
				width: 100vw;
				top: -1rem;
				left: -1rem;
				margin: 0;
				padding-left: 4rem;
				display: flex;
				align-items: center;
				color: white;
				background-color: teal;
			}
		}
	}
</style>
