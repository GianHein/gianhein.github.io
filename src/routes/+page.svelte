<script>
	import * as m from '$lib/paraglide/messages.js';

	import { base } from '$app/paths';

	import Nav from '$components/nav.svelte';
	// import Licensing from '$components/licensing.svelte';

	import { Button } from '$lib/components/ui/button';
	import {
		arrowRight,
		application,
		rendering,
		atom,
		audio,
		galleryVerticalEnd,
		serverSettings,
    computer,
    terminal
	} from '$lib/icons';

	const features = [
		{
			icon: application,
			text: m.home_skills_web()
		},
		{
			icon: computer,
			text: m.home_skills_systems()
		},
		{
			icon: serverSettings,
			text: m.home_skills_servers()
		},
    {
      icon: terminal,
      text: m.home_skills_vimarchbtw()
    }
	];
</script>

<svelte:head>
	<title>Gian Hein - {m.home_tagline()}</title>
</svelte:head>

<div>
	<div class="-z-10">
		<img
			src={`${base}/images/nature.jpg`}
			alt="Atreus"
			class="absolute z-0 max-h-screen min-h-full w-auto min-w-full max-w-full bg-cover object-cover object-top"
		/>
	</div>
	<div class="absolute z-10 w-full scroll-mt-20">
		<Nav />
		<div class="h-fit w-full bg-transparent md:h-screen">
			<div
				class="flex h-screen w-full flex-col bg-gradient-to-t from-background via-transparent to-background/50 px-6"
			>
				<div class="mx-auto md:mt-16 flex w-full max-w-7xl items-center justify-center">
					<img src={`${base}/images/gian-hein.png`} alt="Gian Hein" class="mt-24 h-auto w-full" />
				</div>
				<div class="mx-auto mt-12 flex w-full max-w-7xl flex-1 items-end justify-center pb-28">
					<div class="flex flex-col items-center">
						<p class="text-2xl">{m.home_tagline()}</p>
						<div class="mt-6 flex w-full flex-col gap-4 md:max-w-md md:flex-row md:justify-center">
							<Button href={`${base}/projects`} size="lg" class="text-lg font-normal">
								{m.home_view_projects()}
								<span class="text-lg">{@html arrowRight}</span>
							</Button>
							<Button
                href={`${base}/contact`}
								variant="outline"
								class="border-foreground/20 bg-foreground/5 text-lg font-normal backdrop-blur-md backdrop-filter hover:bg-foreground/20 hover:text-foreground"
								size="lg"
							>
								{m.home_contact_me()}
							</Button>
						</div>
						<div class="mt-8 md:mt-14 flex w-full max-w-7xl flex-col items-center gap-2 xl:flex-row">
							{#each features as { icon, text }}
								<div
									class="flex h-28 w-full flex-1 items-center gap-8 rounded-md bg-background/20 px-8 py-6 backdrop-blur-md backdrop-filter xl:w-fit"
								>
									<span class="text-4xl">{@html icon}</span>
									<p class="text-md">{text}</p>
								</div>
							{/each}
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>
