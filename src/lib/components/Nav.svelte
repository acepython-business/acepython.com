<script>
	import { page } from '$app/stores';
	import { get } from 'svelte/store';

	let currentSection = $state(get(page).url.href);

	/** @type {{links?: import('svelte').Snippet}}*/
	let { links } = $props();
	links ??= defaultLinks;

	const navigation = [
		{ href: '/#about-us', title: 'About Us' },
		{ href: '/#blog', title: 'Blog' },
		{ href: '/#recommendations', title: 'Recommendations' },
		{ href: '/#get-started', title: 'Get Started' }
	];
</script>

{#snippet defaultLinks()}
	{#each navigation as { href, title }}
		<a {href} class:active={currentSection.includes(href)}>{title}</a>
	{/each}
{/snippet}

<div class="nav-container">
	<nav class="container-x nav">
		<a href="/" class="logotype">
			<div class="logo"><img src="logo-light.svg" alt="" /></div>
			<span class="name">AcePython.com</span>
		</a>
		<div class="links">
			{@render links()}
		</div>
		<div class="actions"></div>
	</nav>
</div>

<style>
	.nav-container {
		position: sticky;
		top: 0;
		z-index: 1;
		min-height: var(--layout-nav-height);
		background-color: var(--layout-background-color);
		color: var(--layout-color);
	}

	.nav {
		width: 100%;
		min-height: var(--layout-nav-height);
		display: flex;
		align-items: center;
		flex-wrap: wrap;
		gap: 3rem;
	}

	.links {
		display: flex;
		gap: 1.5rem;
	}

	.logotype {
		font-weight: bold;
		align-self: center;
		justify-self: left;
		display: flex;
		align-items: center;
		font-size: 1.25rem;
		gap: 0.25rem;
		transition: color 1s;
	}

	.logotype:hover {
		color: #ffd43b;
	}

	.logotype .logo {
		height: calc(var(--layout-nav-height) / 2);
		width: 3rem;
	}

	.logotype img {
		height: 90%;
		margin: auto;
		transition: transform 2.5s;
	}

	.logotype:hover img {
		transition: transform 1s;
		transform: rotate(360deg);
	}
</style>
