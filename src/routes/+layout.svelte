<script>
	import '../app.css';
	import logo42 from '$lib/images/42_KL.webp';
</script>

<div class="app">
	<slot />
	<img class=" h-14 fixed right-20 bottom-20 pointer-events-none" src={logo42} alt="42 logo" />
</div>

<style lang="postcss">
	.app {
		@apply w-screen h-screen box-border grid text-white;
	}
</style>
