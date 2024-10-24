<script>
	/** @type {{id: string, children?: import('svelte').Snippet}}*/
	let { id, children } = $props();
</script>

<section {id}>
	<div class="inline-container slide scroll-fade-in">
		{@render children?.()}
	</div>
</section>

<style>
	.slide {
		height: min(calc(100vh - var(--layout-nav-height)), 70em);
		padding-block: var(--layout-padding-block);
		scroll-snap-align: start;
		position: relative;
	}

	@media (prefers-reduced-motion: no-preference) {
		.scroll-fade-in {
			opacity: 0;
			animation: scroll-fade-in linear forwards;
			animation-timeline: view();
			animation-range: 40% 50%;
		}

		@keyframes scroll-fade-in {
			to {
				opacity: 1;
			}
		}
	}
</style>
