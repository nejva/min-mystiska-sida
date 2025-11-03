<script>
	import favicon from '$lib/assets/favicon.svg';
	import {base} from '$app/paths';
	
	let { children } = $props();
</script>

<nav> 
	<a href="{base}/photoapp">Photo App... or Cat App?</a> 
	<a href="{base}/">Hem</a>
</nav>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

{@render children?.()}
