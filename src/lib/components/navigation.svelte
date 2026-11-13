<script lang="ts">
	import LangSwitch from '#lib/components/lang-switch.svelte';
	import { page } from '$app/state';

	const links = [
		{ label: 'Home', href: '/' },
		{ label: 'Upscaling', href: '/upscaling' },
		{ label: 'Pricing', href: '/pricing' }
	];
</script>

<nav class="flex gap-10 p-4">
	<a href="/" class="logo">MyApp</a>

	<ul class="ml-auto flex items-center gap-4">
		{#each links as link}
			<li>
				<a href={link.href} aria-current={page?.url.pathname === link.href ? 'page' : undefined}>
					{link.label}
				</a>
			</li>
		{/each}
	</ul>

	<LangSwitch />
</nav>
