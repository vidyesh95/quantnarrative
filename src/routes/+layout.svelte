<script lang="ts">
	import { Button } from '$lib/components/ui/button';
	import '../app.css';

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
		<Button variant="outline">Sign in</Button>
		<Button>Start Free Trial</Button>
	</div>
</header>

{@render children()}
