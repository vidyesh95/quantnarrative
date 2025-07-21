<script lang="ts">
	import '../app.css';
	import { ModeWatcher } from 'mode-watcher';
	import SunIcon from '@lucide/svelte/icons/sun';
	import MoonIcon from '@lucide/svelte/icons/moon';

	import { resetMode, setMode } from "mode-watcher";
	import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index.js";
	import { buttonVariants } from "$lib/components/ui/button/index.js";
	import { Button } from '$lib/components/ui/button';

	let { children } = $props();
</script>

<header class="flex items-center justify-between px-4 py-2">
	<a href="/" class="flex items-center gap-2">
		<div class="w-8 h-8 flex items-center justify-center rounded-lg bg-gradient-to-br from-[#0DA2E7FF] to-[#36D399FF]">
			<span class="text-lg font-bold text-white">Q</span>
		</div>
		<span class="text-xl font-bold text-foreground">
			QuantNarrative
		</span>
	</a>
	<nav class="space-x-2 md:space-x-8">
		<a href="/eastern-whisper" class="text-lg font-semibold text-foreground">Eastern Whisper</a>
		<a href="/narrative-tracker" class="text-lg font-semibold text-foreground">Narrative Tracker</a>
		<a href="/influential-portfolios" class="text-lg font-semibold text-foreground">Influential Portfolios</a>
	</nav>
	<div class="space-x-1">
		<DropdownMenu.Root>
			<DropdownMenu.Trigger
				class={buttonVariants({ variant: "outline", size: "icon" })}
			>
				<SunIcon
					class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 !transition-all dark:-rotate-90 dark:scale-0"
				/>
				<MoonIcon
					class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 !transition-all dark:rotate-0 dark:scale-100"
				/>
				<span class="sr-only">Toggle theme</span>
			</DropdownMenu.Trigger>
			<DropdownMenu.Content align="end">
				<DropdownMenu.Item onclick={() => setMode("light")}>Light</DropdownMenu.Item
				>
				<DropdownMenu.Item onclick={() => setMode("dark")}>Dark</DropdownMenu.Item>
				<DropdownMenu.Item onclick={() => resetMode()}>System</DropdownMenu.Item>
			</DropdownMenu.Content>
		</DropdownMenu.Root>
		<Button variant="outline" href="/sign-in">
			Sign in
		</Button>
		<Button href="/sign-up">
			Start Free Trial
		</Button>
	</div>
</header>

<ModeWatcher />
{@render children()}
