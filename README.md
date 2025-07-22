# SvelteKit Starter

A modern SvelteKit project with TypeScript, TailwindCSS, and pre-built UI components ready to use.

## Quick Start

```bash
npm install
npm run dev
```

## What's Inside

### Core Technologies

- **SvelteKit 2.22.0** - Full-stack framework with TypeScript
- **TailwindCSS 4.0** - Utility-first CSS framework
- **Vite** - Fast build tool and dev server
- **ESLint + Prettier** - Code linting and formatting

### Ready-to-Use UI Components

All components are in `src/lib/components/ui/` and can be imported like this:

```svelte
import { Button } from '$lib/components/ui/button';
import { Badge } from '$lib/components/ui/badge';
```

Pre-installed components:

- **Button** - Various styles (default, destructive, outline, secondary, ghost, link)
- **Badge** - Small status indicators (default, secondary, destructive, outline)
- **Input** - Form input fields
- **Label** - Form labels
- **Tabs** - Tab navigation
- **Dialog** - Modal dialogs
- **Drawer** - Slide-out panels
- **Command** - Command palette/search
- **Sonner** - Toast notifications

### Quick Examples

```svelte
<script lang="ts>
	import { Button } from '$lib/components/ui/button';
	import { Badge } from '$lib/components/ui/badge';
	import { toast } from 'svelte-sonner';
</script>

<Button onclick={() => toast('Hello!')}>Click me</Button>
<Button onclick={() => toast.error('Not a real error!')}>Click me</Button>

<Badge variant="secondary">New</Badge>
```

### Project Structure

```
src/
├── lib/
│   └── components/
│       ├── ui/           # Reusable UI components
│       └── Onboarding.svelte
├── routes/
│   ├── +layout.svelte    # Global layout
│   └── +page.svelte      # Home page
└── app.html              # HTML template
```

## Development

```bash
npm run dev          # Start dev server
npm run build        # Build for production
npm run preview      # Preview production build
npm run format       # Format code
npm run lint         # Lint code
```

## Features

- Dark/light theme support (mode-watcher)
- TypeScript configured
- Responsive design ready
- Accessible components
- Production optimized
- Easy paste CS from tweakCN
