<script>
	import { i18n } from '$lib/i18n';
	import { ParaglideJS } from '@inlang/paraglide-sveltekit';
	import '../app.css';
  import { base } from '$app/paths';
	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" type="image/svg" href={`${base}/images/logo.svg`} />
</svelte:head>

<ParaglideJS {i18n}>
	{@render children()}
</ParaglideJS>
