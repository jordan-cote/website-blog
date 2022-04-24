<script context="module" lang="ts">
	/** @type {import('@sveltejs/kit').Load} */
	export function load({ error, status }) {
		return {
			props: {
				title: `${status}: ${error.message}`
			}
		};
	}

	let title: string;
</script>

<h1>error: {title}</h1>
