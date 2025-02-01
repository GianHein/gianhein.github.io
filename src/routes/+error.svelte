<script>
	import Nav from '$components/Nav.svelte';

  import { base } from '$app/paths';
  import { page } from '$app/stores';
</script>

<svelte:head>
	<title>Gian Hein - Error</title>
</svelte:head>

<Nav />

<div class="relative h-[17vh] max-h-64 min-h-24 bg-gradient-to-b from-secondary/50 to-background">
	<div class="mx-auto flex w-full max-w-7xl px-6">
	</div>
</div>

<div class="mx-auto mt-12 w-fit px-6">
  <img src={`${base}/images/404.svg`} alt="Error" class="w-full h-auto max-w-md mx-auto" />
	<h1 class="font-archivo text-4xl md:text-6xl mt-8 text-center">{$page.status}</h1>
	<p class="text-xl text-muted-foreground text-center">{$page.error.message}</p>
</div>


