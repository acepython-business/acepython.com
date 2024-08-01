<script>
	/** @type {{children?: import('svelte').Snippet}}*/
	let { children } = $props();
</script>

<footer>
	{@render children?.()}
</footer>
