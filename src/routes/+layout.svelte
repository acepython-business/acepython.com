<script>
	import { Nav, Footer } from '$lib/components';

	import { getContext } from 'svelte';

	let { children } = $props();
</script>

<section>
	<div class="container nav">
		<Nav />
	</div>
</section>
<main>
	<div class="container">
		{@render children()}
	</div>
</main>
<section>
	<div class="container">
		<Footer>&copy; AcePython.com</Footer>
	</div>
</section>

<style>
	:global(:root) {
		--python-blue-base: rgb(55, 118, 171);
		--python-blue-dark: rgb(44, 90, 134);
		--python-blue-darker: rgb(34, 70, 104);
		--python-blue-bright: rgb(74, 141, 192);
		--python-blue-brighter: rgb(95, 160, 212);

		--python-yellow-base: rgb(255, 211, 67);
		--python-yellow-dark: rgb(204, 170, 54);
		--python-yellow-darker: rgb(163, 135, 43);
		--python-yellow-bright: rgb(255, 224, 102);
		--python-yellow-brighter: rgb(255, 237, 140);

		--layout-padding-inline: min(1.5rem, 5vw);
		--layout-padding-block: min(1.5rem, 5vh);
		--layout-max-width: 80rem;
	}

	:global(*) {
		box-sizing: border-box;
	}

	:global(html, body) {
		margin: 0;
		padding: 0;
	}

	:global(body) {
		background-color: var(--python-blue-darker);
		font-family: Ubuntu;
		color: var(--python-yellow-brighter);
		display: grid;
		grid-template-rows: auto 1fr auto;
		min-height: 100vh;
	}

	:global(a) {
		text-decoration: none;
		color: unset;
	}

	main,
	section {
		width: 100%;
		display: flex;
		justify-content: center;
	}

	.nav {
		width: unset;
	}

	:global(.container) {
		width: 100%;
		max-width: var(--layout-max-width);
		padding-block: var(--layout-padding-block);
		padding-inline: var(--layout-padding-inline);
		margin-inline: auto;
	}
</style>
