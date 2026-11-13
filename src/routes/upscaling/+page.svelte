<script lang="ts">
	import { Button } from '#lib/components/ui/button/index.ts';
	import { m } from '#lib/paraglide/messages.js';
</script>

<Button>Hello</Button>
<h1>{m.hello_world({ name: 'SvelteKit User' })}</h1>
