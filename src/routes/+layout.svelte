<script>
	import '../app.css';
</script>

<div class="app">
	<slot />
</div>

<style lang="postcss">
	.app {
		@apply w-screen h-screen box-border grid text-white;
	}
</style>
