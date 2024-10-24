<script>
	import { Nav, Footer } from '$lib/components';

	import '../reset.css';
	import '../root.css';

	let { children } = $props();
</script>

<Nav />
<main>
	{@render children()}
</main>
<Footer>&copy; AcePython.com</Footer>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Signika:wght@300..700&display=swap');

	:global(*) {
		box-sizing: border-box;
	}

	:global(html) {
		scroll-padding-top: var(--layout-nav-height);
		@media (prefers-reduced-motion: no-preference) {
			scroll-behavior: smooth;
			scroll-snap-type: block proximity;
		}
	}

	:global(body) {
		background-color: var(--theme-bg-color-1);
		color: var(--theme-color);
		font-family: Signika, sans-serif;
		font-size: 1rem;
		display: flex;
		flex-direction: column;
		position: relative;
		min-height: 100vh;
	}

	:global(a) {
		text-decoration: none;
		color: unset;
	}

	:global(.inline-container) {
		width: 100%;
		max-width: var(--layout-max-width);
		padding-inline: var(--layout-padding-inline);
		margin-inline: auto;
	}

	:global(.block-container) {
		padding-block: var(--layout-padding-block);
	}

	main {
		width: 100%;
		flex: 1;
		scroll-behavior: smooth;
		padding-block: unset;
	}
</style>
