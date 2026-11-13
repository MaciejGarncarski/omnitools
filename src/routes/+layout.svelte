<script lang="ts">
	import type { Path } from '$app/types';
	import { resolve } from '$app/paths';
	import { page } from '$app/state';
	import { locales, localizeHref } from '#lib/paraglide/runtime.js';
	import './layout.css';
	import favicon from '#lib/assets/favicon.svg';
	import type { LayoutProps } from './$types';
	import Navigation from '#lib/components/navigation.svelte';

	export const prerender = true;

	let { children }: LayoutProps = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div>
	<Navigation />

	{@render children()}

	<div style="display:none">
		{#each locales as locale (locale)}
			<a href={resolve(localizeHref(page.url.pathname, { locale }) as Path)}>{locale}</a>
		{/each}
	</div>
</div>
