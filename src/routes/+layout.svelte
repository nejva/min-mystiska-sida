<script>
	import favicon from '$lib/assets/favicon.svg';
	import {base} from '$app/paths';
	
	let { children } = $props();
</script>

<nav> 
	<a href="{base}/photoapp">Cat App</a> 
	<a href="{base}/register">Register</a>
	<a href="{base}/">Hem</a>
	<a href="{base}/shoppinglist">Shoppinglist</a>
	<a href="{base}/memory">Memory</a>
	
</nav>

<style>
	:global(body), :global(html){
  margin: 0%;
  padding: 0%;
  height: 100vh;
  width: 100vw;
}
</style>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

{@render children?.()}
