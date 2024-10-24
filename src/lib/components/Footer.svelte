<script>
	/** @type {{children?: import('svelte').Snippet}}*/
	let { children } = $props();
</script>

<div class="footer-container">
	<footer class="inline-container block-container">
		{@render children?.()}
	</footer>
</div>

<style>
	.footer-container {
		background-color: var(--layout-background-color);
		color: var(--layout-color);
	}
</style>
