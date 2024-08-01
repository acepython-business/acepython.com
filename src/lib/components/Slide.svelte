<script>
	/** @type {{id: string, children?: import('svelte').Snippet}}*/
	let { id, children } = $props();
</script>

<section {id} class="slide">
	{@render children?.()}
</section>

<style>
	:global(.slide) {
		min-height: 100vh;
	}
</style>
