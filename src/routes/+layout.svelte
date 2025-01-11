<script>
	import '../app.css';
	let { children } = $props();
</script>

{@render children()}


<style>
	:global(body) {
		background: black;
	}
</style>