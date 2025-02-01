<script>
	import { base } from '$app/paths';
	import { i18n } from '$lib/i18n';
	import { page } from '$app/state';
	import { goto } from '$app/navigation';
	import * as m from '$lib/paraglide/messages.js';
	import { languageTag } from '$lib/paraglide/runtime.js';

	/**
	 * @param {import("$lib/paraglide/runtime").AvailableLanguageTag} newLanguage
	 */
	function switchToLanguage(newLanguage) {
		const canonicalPath = i18n.route(page.url.pathname);
		const localisedPath = i18n.resolveRoute(canonicalPath, newLanguage);
		goto(localisedPath);
	}

	import { Button } from '$lib/components/ui/button';
	import * as DropdownMenu from '$lib/components/ui/dropdown-menu/index.js';
	import * as Accordion from '$lib/components/ui/accordion/index.js';

	import {
		home,
		chevronDown,
		arrowUpRight,
		books,
		fileText,
		gitCommit,
		languages,
		message,
		flagGermany,
		flagUSA,
		more,
		bookRecommendation,
		shapes,
		pack,
		packageOpen,
		check,
		trafficCone
	} from '$lib/icons';

	const links = [
		{
			label: m.nav_home(),
			href: `${base}/`,
			icon: home
		},
		{
			label: m.nav_projects(),
			items: [
				{ label: m.nav_projects_overview(), href: '{base}/projects', icon: shapes },
				{ label: 'Portfolio', href: `${base}/`, icon: check },
				{ label: 'Jade Engine', href: 'https://github.com/gianhein/jade', icon: check, external: true },
				{ label: 'Pikuma Engine', href: `${base}/projects`, icon: trafficCone }
			],
			icon: pack
		},
		{
			label: m.nav_resume(),
			href: `${base}/resume`,
			icon: fileText
		}
		/*
		{
			label: m.nav_more(),
			icon: more
		}
    */
	];

	const langs = [
		{ label: 'English', icon: flagUSA, value: 'en' },
		{ label: 'Deutsch', icon: flagGermany, value: 'de-de' }
	];

	let language = $state(langs.find((lang) => lang.value == languageTag())?.value);
	let cachedLanguage = $state(langs[0].value);

	$effect(() => {
		if (language !== cachedLanguage) {
			switchToLanguage(language);
			cachedLanguage = language;
		}
	});
</script>

<nav class="fixed left-0 top-0 z-20 flex h-16 w-full max-w-full backdrop-blur-lg backdrop-filter">
	<div class="mx-0 flex h-full w-full max-w-7xl items-center justify-between px-6 md:mx-auto">
		<div class="flex flex-1 items-center xl:hidden">
			<DropdownMenu.Root>
				<DropdownMenu.Trigger>
					<div
						class="flex items-center gap-2 rounded-full bg-foreground/30 px-4 py-1.5 backdrop-blur backdrop-filter transition-colors hover:bg-foreground/40"
					>
						Menu
						<span>
							{@html chevronDown}
						</span>
					</div>
				</DropdownMenu.Trigger>
				<DropdownMenu.Content
					side="bottom"
					align="start"
					class="w-64 overflow-visible border-none bg-background/20 p-2 backdrop-blur-md backdrop-filter"
				>
					<DropdownMenu.Group>
						{#each links as element, index}
							{#if !element.items}
								<DropdownMenu.Item
									class="my-1 data-[highlighted]:cursor-pointer data-[highlighted]:bg-background/20 data-[highlighted]:text-foreground"
								>
									<a
										href={element.href}
										target={element.external ? '_blank' : '_self'}
										class="flex w-full items-center"
									>
										<span class="mr-2 text-lg">{@html element.icon}</span>
										{element.label}
										{#if element.external}
											<span class="ml-auto text-lg">{@html arrowUpRight}</span>
										{/if}
									</a>
								</DropdownMenu.Item>
								{#if index < links.length - 1}
									<div class="mx-2 h-px bg-foreground/20"></div>
								{/if}
							{:else}
								<Accordion.Root>
									<Accordion.Item class="border-none">
										<Accordion.Trigger
											class="my-1 rounded-sm px-2 py-1.5 text-sm font-normal transition-colors hover:bg-background/20 hover:no-underline data-[highlighted]:cursor-pointer data-[state=open]:bg-background/20"
										>
											<div class="flex items-center">
												<span class="mr-2 text-lg">{@html element.icon}</span>
												{element.label}
											</div>
										</Accordion.Trigger>
										<Accordion.Content>
											<div class="flex">
												<div class="ml-4 mr-2 w-px bg-foreground/20"></div>
												<div class="flex flex-1 flex-col gap-1">
													{#each element.items as item}
														<a
															href={item.href}
															target={item.external ? '_blank' : '_self'}
															class="flex items-center rounded-sm px-2 py-1.5 text-sm font-normal transition-colors hover:bg-background/20 hover:no-underline data-[highlighted]:cursor-pointer"
														>
															{#if item.icon}
																<span class="mr-2 text-lg">{@html item.icon}</span>
															{/if}
															{item.label}
															{#if item.external}
																<span class="ml-auto text-lg">{@html arrowUpRight}</span>
															{/if}
														</a>
													{/each}
												</div>
											</div>
										</Accordion.Content>
									</Accordion.Item>
								</Accordion.Root>
								{#if index < links.length - 1}
									<div class="mx-2 h-px bg-foreground/20"></div>
								{/if}
							{/if}
						{/each}
						<div class="mx-2 h-px bg-foreground/20 md:hidden"></div>
						<Button
              href={`${base}/contact`}
							class="mt-2 flex w-full justify-start bg-foreground text-background backdrop-blur-md backdrop-filter hover:bg-foreground/90 md:hidden"
						>
							<span class="text-lg">{@html message}</span>
							{m.nav_contact()}
						</Button>
					</DropdownMenu.Group>
				</DropdownMenu.Content>
			</DropdownMenu.Root>
		</div>
		<div class="hidden flex-1 items-center gap-3 xl:flex">
			{#each links as element}
				{#if !element.items}
					<a
						href={element.href}
						target={element.external ? '_blank' : '_self'}
						class="flex items-center gap-2 rounded-full bg-foreground/30 px-4 py-1.5 backdrop-blur backdrop-filter transition-colors hover:bg-foreground/40"
					>
						<span class="text-lg">{@html element.icon}</span>
						{element.label}
						{#if element.external}
							<span>{@html arrowUpRight}</span>
						{/if}
					</a>
				{:else}
					<DropdownMenu.Root>
						<DropdownMenu.Trigger>
							<div
								class="flex items-center gap-2 rounded-full bg-foreground/30 px-4 py-1.5 backdrop-blur backdrop-filter transition-colors hover:bg-foreground/40"
							>
								<span class="text-lg">{@html element.icon}</span>
								{element.label}
								<span>{@html chevronDown}</span>
							</div>
						</DropdownMenu.Trigger>
						<DropdownMenu.Content
							side="bottom"
							align="start"
							class="divide-y-foreground w-64 border border-foreground/20 bg-background/20 p-2 backdrop-blur-md backdrop-filter"
						>
							<DropdownMenu.Group>
								{#each element.items as item, index}
									<DropdownMenu.Item
										class="my-1 flex items-center data-[highlighted]:cursor-pointer data-[highlighted]:bg-background/20 data-[highlighted]:text-foreground"
									>
										<a
											href={item.href}
											target={item.external ? '_blank' : '_self'}
											class="flex w-full items-center"
										>
											{#if item.icon}
												<span class="mr-2 text-lg">{@html item.icon}</span>
											{/if}
											{item.label}
											{#if item.external}
												<span class="ml-auto">{@html arrowUpRight}</span>
											{/if}
										</a>
									</DropdownMenu.Item>
									{#if index < element.items.length - 1}
										<div class="mx-2 h-px bg-foreground/20"></div>
									{/if}
								{/each}
							</DropdownMenu.Group>
						</DropdownMenu.Content>
					</DropdownMenu.Root>
				{/if}
			{/each}
		</div>
		<div class="flex items-center justify-end gap-2">
			<DropdownMenu.Root>
				<DropdownMenu.Trigger>
					<Button
						variant="transparent"
						class="border border-foreground/20 bg-foreground/30 backdrop-blur-md backdrop-filter hover:bg-foreground/40"
					>
						<span class="text-lg">{@html languages}</span>
						{langs.find((lang) => lang.value === language)?.label}
						<span>
							{@html chevronDown}
						</span>
					</Button>
				</DropdownMenu.Trigger>
				<DropdownMenu.Content
					side="bottom"
					align="end"
					class="divide-y-foreground w-56 border border-foreground/20 bg-background/20 p-2 backdrop-blur-md backdrop-filter"
				>
					<DropdownMenu.Group>
						<DropdownMenu.RadioGroup bind:value={language}>
							{#each langs as lang}
								<DropdownMenu.RadioItem
									value={lang.value}
									class="my-1 flex items-center data-[highlighted]:cursor-pointer data-[highlighted]:bg-background/20 data-[highlighted]:text-foreground"
								>
									<span class="mr-2 text-lg">{@html lang.icon}</span>
									{lang.label}
								</DropdownMenu.RadioItem>
								{#if lang !== langs[langs.length - 1]}
									<div class="mx-2 h-px bg-foreground/20"></div>
								{/if}
							{/each}
						</DropdownMenu.RadioGroup>
					</DropdownMenu.Group>
				</DropdownMenu.Content>
			</DropdownMenu.Root>

			<Button
        href={`${base}/contact`}
				class="hidden bg-foreground text-background backdrop-blur-md backdrop-filter hover:bg-foreground/90 md:flex"
			>
				<span class="text-lg">{@html message}</span>
				{m.nav_contact()}
			</Button>
		</div>
	</div>
</nav>
