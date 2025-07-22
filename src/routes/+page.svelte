<script lang="ts">
	import { Button } from '$lib/components/ui/button';
	import { toast } from 'svelte-sonner';
</script>

<div class="mx-auto flex min-h-svh max-w-screen-sm flex-col">
	<div class="flex flex-1 flex-col items-center justify-center gap-4 p-8 text-center">
		<h1>SvelteKit 2.22.0 & ShadCN Svelte Boilerplate</h1>

		<p>
			Edit <code>src/routes/+layout.svelte</code> to see the layout changes.
		</p>
		<p>
			Edit <code>src/routes/+page.svelte</code> to see the page changes.
		</p>

		<Button onclick={() => toast.success('Ready to MVP ✨')}>Show Toast</Button>
	</div>
</div>
