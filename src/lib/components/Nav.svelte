<script>
	/** @type {{navChildren?: import('svelte').Snippet}}*/
	let { navChildren } = $props();
	navChildren ??= defaultChildren;
</script>

{#snippet defaultChildren()}
	<ul><a href="/">Link 1</a></ul>
	<ul><a href="/">Link 2</a></ul>
	<ul><a href="/">Link 3</a></ul>
{/snippet}

<nav>{@render navChildren()}</nav>
<div>{@render navChildren()}</div>

<style>
	nav,
	div {
		display: flex;
	}

	div {
		visibility: hidden;
	}

	nav {
		position: fixed;
		left: 50%;
		transform: translate(-50%);
	}
</style>
