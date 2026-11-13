<script lang="ts">
	import { page } from '$app/state';
	import { locales, getLocale, localizeHref } from '#lib/paraglide/runtime.js';

	const currentPath = $derived(page.url.pathname as Parameters<typeof localizeHref>[0]);
</script>

<nav>
	{#each locales as locale}
		<a
			href={localizeHref(currentPath, { locale })}
			aria-current={getLocale() === locale ? 'page' : undefined}
		>
			{locale.toUpperCase()}
		</a>
	{/each}
</nav>
