<script>
	import Footer from "../components/general/Footer.svelte";
	import Header from "../components/general/Header.svelte";
	import "../global.scss";
</script>

<div style="overflow: hidden;">
	<Header />
	<div class="content-fit">
		<div>
			<slot />
		</div>
	</div>
	<Footer />
</div>

<style lang="scss">
	.content-fit {
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		height: 100vh;
	}
</style>
