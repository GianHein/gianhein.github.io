<script>
	import * as m from '$lib/paraglide/messages.js';

	import { arrowUpRight } from '$lib/icons';

	import Nav from '$components/nav.svelte';
</script>

<svelte:head>
	<title>Gian Hein - {m.contact_title()}</title>
</svelte:head>

<Nav />

<div class="relative h-[17vh] max-h-64 min-h-24 bg-gradient-to-b from-secondary/50 to-background">
	<div class="mx-auto flex w-full max-w-7xl px-6">
		<h1 class="absolute bottom-0 font-archivo text-4xl md:text-6xl">{m.contact_title()}</h1>
	</div>
</div>

<div class="mx-auto mt-12 max-w-7xl px-6">
	<p class="text-xl text-muted-foreground">{m.contact_description()}</p>
</div>

<div class="mx-auto mt-12 flex w-full max-w-7xl px-6 pb-12">
	<div class="flex w-full gap-8">
		<div class="flex flex-1 flex-col gap-4">
			<div>
				<h3 class="text-xl font-semibold">{m.contact_email()}</h3>
				<a class="text-primary underline" href="mailto:gian.hein@gmail.com">
					gian.hein@gmail.com
				</a>
			</div>
			<div>
				<h3 class="text-xl font-semibold">{m.contact_phone()}</h3>
				<p>+49(0) 176 4313 4806</p>
			</div>
		</div>
		<div class="flex flex-1 flex-col gap-4">
			<div>
				<h3 class="text-xl font-semibold">{m.contact_linkedin()}</h3>
				<a
					class="text-primary underline flex items-center gap-1"
					href="https://www.linkedin.com/in/gian-hein-3a6045349/"
					target="_blank"
				>
					Gian Hein
          <span class="text-lg">{@html arrowUpRight}</span>
				</a>
			</div>
		</div>
	</div>
</div>
