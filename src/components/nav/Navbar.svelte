<script>
	import HamburgerButton from "./HamburgerButton.svelte";
	import NavContent from "./NavContent.svelte";
</script>

<nav>
	<HamburgerButton>
		<svelte:fragment slot="test">
			<NavContent />
		</svelte:fragment>
	</HamburgerButton>

	<div class="not-mobile">
		<NavContent />
	</div>
</nav>

<style lang="scss">
	@import "../../constants.scss";

	nav {
		background-color: rgba($color: rgb(99, 161, 161), $alpha: 1);
		$h-offset: 0px;
		$v-offset: 5px;
		$blur: 30px;
		box-shadow: rgb(177, 233, 233) $h-offset $v-offset $blur;
		-webkit-user-select: none;
		user-select: none;

		@media (max-width: 1000px) {
			.not-mobile {
				display: none;
			}

			
		}
	}
</style>
