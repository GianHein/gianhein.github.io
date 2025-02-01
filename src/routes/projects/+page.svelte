<script>
	import * as m from '$lib/paraglide/messages.js';

	import { base } from '$app/paths';
	import { Button } from '$lib/components/ui/button';
	import { Badge } from '$lib/components/ui/badge/index.js';

	import Nav from '$components/Nav.svelte';

	import { arrowRight } from '$lib/icons';

	const statuses = [
		{ name: m.projects_status_in_progress() },
		{ name: m.projects_status_finished() }
	];

	const projects = [
		{
			name: m.projects_portfolio_title(),
			date: m.projects_portfolio_date(),
			status: 1,
			preview: `${base}/images/project-portfolio.jpeg`,
			description: m.projects_portfolio_description(),
			skills: ['Svelte', 'TailwindCSS', 'Paraglide'],
			link: '/'
		},
		{
			name: 'Jade Engine',
			date: m.projects_jade_date(),
			status: 1,
			preview: `${base}/images/project-jade.jpg`,
			description: m.projects_jade_description(),
			skills: ['Java', 'GLSL', 'OpenGL', 'GLFW', 'LWJGL', 'JOML', 'Dear ImGui'],
			link: 'https://github.com/gianhein/jade'
		},
		{
			name: 'Pikuma Engine',
			date: m.projects_pikuma_date(),
			status: 0,
			preview: `${base}/images/project-pikuma.png`,
			description: m.projects_pikuma_description(),
			skills: ['C++', 'SDL', 'GLM', 'Dear ImGui', 'Sol', 'Lua']
		}
	];
</script>

<svelte:head>
	<title>Gian Hein - {m.projects_title()}</title>
</svelte:head>

<Nav />

<div class="relative h-[17vh] max-h-64 min-h-24 bg-gradient-to-b from-secondary/50 to-background">
	<div class="mx-auto flex w-full max-w-7xl px-6">
		<h1 class="absolute bottom-0 font-archivo text-4xl md:text-6xl">{m.projects_title()}</h1>
	</div>
</div>

<div class="mx-auto mt-12 max-w-7xl px-6">
	<p class="text-xl text-muted-foreground">{m.projects_description()}</p>
</div>

<div
	class="mx-auto mt-12 grid w-full max-w-7xl grid-cols-1 gap-8 px-6 pb-12 md:grid-cols-2 lg:grid-cols-3"
>
	{#each projects as project}
		<div class="col-span-1 flex flex-col divide-y rounded-md border">
			<img
				src={project.preview}
				alt={project.name}
				class="aspect-video w-full rounded-t-md object-cover object-center"
			/>
			<div class="flex h-full flex-col p-3">
				<div class="flex items-center justify-between">
					<span class="mb-1 font-mono text-xs text-muted-foreground">{project.date}</span>
					{#if project.status === 0}
						<Badge variant="default">{statuses[project.status].name}</Badge>
					{:else if project.status === 1}
						<Badge class="bg-green-500 text-background hover:bg-green-500/80"
							>{statuses[project.status].name}</Badge
						>
					{/if}
				</div>
				<h2 class="text-2xl">{project.name}</h2>
				<div class="my-3 flex flex-wrap gap-2">
					{#each project.skills as skill}
						<Badge variant="outline">{skill}</Badge>
					{/each}
				</div>
				<p class="mb-3 text-muted-foreground">
					{project.description}
				</p>
				{#if project.link}
					<div class="mt-auto flex flex-1 items-end">
						<Button href={project.link} target="_blank" variant="transparent" class="border bg-foreground/10 hover:bg-foreground/30">
							{m.projects_view_project()}
							<span class="text-xl">{@html arrowRight}</span>
						</Button>
					</div>
				{/if}
			</div>
		</div>
	{/each}
</div>
