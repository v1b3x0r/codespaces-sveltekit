<script lang="ts">
	import '../app.css';
	import { Toaster } from '$lib/components/ui/sonner/';

	let { children } = $props();
</script>

<div class="relative min-h-svh">
	<Toaster richColors position="top-center" />

	<!-- content container -->
	<main class="container mx-auto">
		{@render children()}
	</main>
</div>
