<script lang="ts">
	import '../app.css';
	import { Toaster } from '$lib/components/ui/sonner/';
	import { ModeWatcher } from 'mode-watcher';

	let { children } = $props();
</script>

<div class="relative min-h-svh">
	<Toaster richColors position="top-center" />
	<ModeWatcher />

	<!-- content container -->
	<main class="container mx-auto">
		{@render children()}
	</main>
</div>
