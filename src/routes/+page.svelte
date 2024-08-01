<script>
	import Slide from '$lib/components/Slide.svelte';
</script>

{#snippet navChildren()}
	<ul><a href="/">Link 1</a></ul>
	<ul><a href="/">Link 2</a></ul>
	<ul><a href="/">Link 3</a></ul>
{/snippet}

<div class="slides">
	<Slide id="intro">
		<h1>Slide 1</h1>
	</Slide>
	<Slide id="products">
		<h1>Slide 2</h1>
	</Slide>
</div>

<style>
	.slides {
		scroll-padding-top: 1em;
		scroll-snap-type: y mandatory;
		scroll-behavior: smooth;
	}

	.slides > * {
		scroll-snap-align: center;
	}
</style>
