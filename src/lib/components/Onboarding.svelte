<script lang="ts">
	import { Button } from '$lib/components/ui/button';
	import { Badge } from '$lib/components/ui/badge';
	import { toast } from 'svelte-sonner';
	import {
		GithubIcon,
		ZapIcon,
		SparklesIcon,
		Code2Icon,
		PaletteIcon,
		RocketIcon,
		CheckCircleIcon,
		MonitorIcon,
		ShieldCheckIcon
	} from '@lucide/svelte';

	const features = [
		{
			icon: ZapIcon,
			title: 'SvelteKit 2.22.0',
			description: 'Latest SvelteKit with TypeScript support and file-based routing'
		},
		{
			icon: PaletteIcon,
			title: 'ShadCN Svelte',
			description: 'Beautiful, accessible UI components with dark/light theme'
		},
		{
			icon: SparklesIcon,
			title: 'TailwindCSS 4.0',
			description: 'Utility-first CSS with custom theme and responsive design'
		},
		{
			icon: MonitorIcon,
			title: 'Developer Experience',
			description: 'ESLint, Prettier, TypeScript, and Vite for optimal DX'
		},
		{
			icon: ShieldCheckIcon,
			title: 'Production Ready',
			description: 'Pre-configured with best practices and security in mind'
		},
		{
			icon: CheckCircleIcon,
			title: 'Codespace Optimized',
			description: 'Ready-to-use GitHub Codespaces configuration'
		}
	];

	const techStack = [
		'SvelteKit',
		'TypeScript',
		'TailwindCSS',
		'ShadCN Svelte',
		'ESLint',
		'Prettier',
		'Vite',
		'GitHub Codespaces'
	];

	const quickStartSteps = [
		{
			method: 'GitHub Codespaces',
			icon: GithubIcon,
			recommended: true,
			steps: [
				'Click "Use this template" → "Create codespace"',
				'Wait for auto-setup to complete',
				'Server starts automatically on port 4000',
				'Start building your amazing app!'
			]
		},
		{
			method: 'Local Development',
			icon: Code2Icon,
			recommended: false,
			steps: ['git clone <your-repo>', 'npm install', 'npm run dev', 'Open http://localhost:4000']
		}
	];

	function handleGetStarted() {
		toast.success('🚀 Ready to build something amazing!');
		// You can add navigation logic here
	}

	function handleViewGithub() {
		toast.info('🔗 Open your repository to explore the code');
		// window.open('https://github.com/your-username/your-repo', '_blank');
	}
</script>

<svelte:head>
	<title>Welcome to SvelteKit + ShadCN Svelte Boilerplate</title>
	<meta
		name="description"
		content="Production-ready SvelteKit boilerplate with ShadCN Svelte components, TypeScript, and Codespaces support"
	/>
</svelte:head>

<div class="min-h-screen bg-gradient-to-br from-background via-background to-muted/20">
	<!-- Hero Section -->
	<div class="mx-auto max-w-7xl px-6 py-16 lg:py-24">
		<div class="text-center">
			<!-- Welcome Badge -->
			<div class="mb-8">
				<Badge variant="secondary" class="px-4 py-2 text-sm font-medium">
					<RocketIcon class="mr-2 h-4 w-4" />
					Welcome to Your New Project
				</Badge>
			</div>

			<!-- Main Heading -->
			<h1
				class="mb-8 bg-gradient-to-r from-foreground to-foreground/70 bg-clip-text text-5xl font-bold tracking-tight text-transparent sm:text-7xl"
			>
				SvelteKit + ShadCN
				<br />
				<span class="bg-gradient-to-r from-primary to-primary/70 bg-clip-text text-transparent">
					Boilerplate
				</span>
			</h1>

			<!-- Subtitle -->
			<p class="mx-auto mb-12 max-w-3xl text-xl text-muted-foreground sm:text-2xl">
				A modern, production-ready template with beautiful UI components, TypeScript support, and
				best practices built-in. Perfect for your next project.
			</p>

			<!-- CTA Buttons -->
			<div class="flex flex-col gap-4 sm:flex-row sm:justify-center">
				<Button size="lg" class="h-14 px-10 text-lg" onclick={handleGetStarted}>
					<Code2Icon class="mr-2 h-5 w-5" />
					Start Building
				</Button>

				<Button variant="outline" size="lg" class="h-14 px-10 text-lg" onclick={handleViewGithub}>
					<GithubIcon class="mr-2 h-5 w-5" />
					View on GitHub
				</Button>
			</div>
		</div>

		<!-- Features Grid -->
		<div class="mt-32">
			<div class="mb-16 text-center">
				<h2 class="text-4xl font-bold tracking-tight">Everything You Need</h2>
				<p class="mt-6 text-xl text-muted-foreground">
					Pre-configured with modern tools and best practices for rapid development
				</p>
			</div>

			<div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
				{#each features as feature}
					<div
						class="group rounded-xl border bg-card p-8 text-center transition-all hover:bg-accent hover:shadow-lg"
					>
						<div
							class="mx-auto mb-6 flex h-16 w-16 items-center justify-center rounded-xl bg-primary/10 transition-colors group-hover:bg-primary/20"
						>
							<svelte:component this={feature.icon} class="h-8 w-8 text-primary" />
						</div>
						<h3 class="mb-4 text-xl font-semibold">{feature.title}</h3>
						<p class="leading-relaxed text-muted-foreground">{feature.description}</p>
					</div>
				{/each}
			</div>
		</div>

		<!-- Tech Stack -->
		<div class="mt-32">
			<div class="mb-12 text-center">
				<h2 class="text-3xl font-bold tracking-tight">Tech Stack</h2>
				<p class="mt-4 text-lg text-muted-foreground">
					Built with modern, proven technologies for scalability and maintainability
				</p>
			</div>

			<div class="flex flex-wrap justify-center gap-3">
				{#each techStack as tech}
					<Badge variant="outline" class="px-4 py-2 text-sm font-medium">
						{tech}
					</Badge>
				{/each}
			</div>
		</div>

		<!-- Quick Start Section -->
		<div class="mt-32">
			<div class="mb-12 text-center">
				<h2 class="text-3xl font-bold tracking-tight">Quick Start</h2>
				<p class="mt-4 text-lg text-muted-foreground">Choose your preferred development method</p>
			</div>

			<div class="grid gap-8 lg:grid-cols-2">
				{#each quickStartSteps as method}
					<div class="rounded-xl border bg-card p-8">
						<div class="mb-6 flex items-center justify-between">
							<div class="flex items-center gap-3">
								<div class="flex h-12 w-12 items-center justify-center rounded-lg bg-primary/10">
									<svelte:component this={method.icon} class="h-6 w-6 text-primary" />
								</div>
								<h3 class="text-xl font-semibold">{method.method}</h3>
							</div>
							{#if method.recommended}
								<Badge variant="default" class="text-xs">Recommended</Badge>
							{/if}
						</div>

						<div class="space-y-3">
							{#each method.steps as step, index}
								<div class="flex items-center gap-3">
									<div
										class="mt-1 flex h-6 w-6 shrink-0 items-center justify-center rounded-full bg-primary/20 text-xs font-semibold text-primary"
									>
										{index + 1}
									</div>
									<p class="text-sm text-muted-foreground">{step}</p>
								</div>
							{/each}
						</div>

						{#if method.recommended}
							<div class="mt-6 rounded-lg bg-primary/5 p-4">
								<p class="text-sm text-primary">
									✨ <strong>Pro tip:</strong> Codespaces automatically configures everything for you!
								</p>
							</div>
						{/if}
					</div>
				{/each}
			</div>
		</div>

		<!-- Next Steps -->
		<div class="mt-32 rounded-2xl border bg-card p-12">
			<div class="mb-8 text-center">
				<h2 class="text-3xl font-bold tracking-tight">What's Next?</h2>
				<p class="mt-4 text-lg text-muted-foreground">
					Ready to start building? Here are some next steps
				</p>
			</div>

			<div class="grid gap-6 md:grid-cols-3">
				<Button
					variant="outline"
					class="h-20 flex-col gap-2"
					onclick={() => toast('📚 Explore the documentation and examples')}
				>
					<span class="text-2xl">📚</span>
					<span>Read Documentation</span>
				</Button>

				<Button
					variant="outline"
					class="h-20 flex-col gap-2"
					onclick={() => toast('🎨 Check out all available UI components')}
				>
					<span class="text-2xl">🎨</span>
					<span>Explore Components</span>
				</Button>

				<Button
					variant="outline"
					class="h-20 flex-col gap-2"
					onclick={() => toast('⚡ Start customizing your app')}
				>
					<span class="text-2xl">⚡</span>
					<span>Start Customizing</span>
				</Button>
			</div>
		</div>

		<!-- Footer -->
		<div class="mt-24 text-center">
			<p class="text-lg text-muted-foreground">
				Built with ❤️ using <span class="font-semibold text-primary">SvelteKit</span> &
				<span class="font-semibold text-primary">ShadCN Svelte</span>
			</p>
			<p class="mt-2 text-sm text-muted-foreground">
				Remove this onboarding page and start building your amazing project!
			</p>
		</div>
	</div>
</div>

<style>
	:global(html) {
		scroll-behavior: smooth;
	}
</style>
