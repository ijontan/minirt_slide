<script lang="ts">
	import Slide1 from './Slide1.svelte';
	import Slide2 from './Slide2.svelte';
	import Slide3 from './Slide3.svelte';
	import Slide4 from './Slide4.svelte';
	import Slide5 from './Slide5.svelte';
	import Slide6 from './Slide6.svelte';

	const firstPage = 0;
	const lastPage = 6;
	let page = firstPage;

	function prevPage() {
		if (page == firstPage) return;
		page -= 1;
	}
	function nextPage() {
		if (page == lastPage) return;
		page += 1;
	}

	function onKeyDown(e: KeyboardEvent) {
		if (e.key == 'ArrowRight') nextPage();
		else if (e.key == 'ArrowLeft') prevPage();
		else if (e.key == 'l') nextPage();
		else if (e.key == 'h') prevPage();
		else if (e.key == 'j') nextPage();
		else if (e.key == 'k') prevPage();
	}
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<svelte:window on:keydown={onKeyDown} on:click={nextPage} />

{#if page == 0 || page == 1}
	<Slide1 open={page == 1} />
{:else if page == 2}
	<Slide2 />
{:else if page == 3}
	<Slide3 />
{:else if page == 4}
	<Slide6 />
{:else if page == 5}
	<Slide4 />
{:else if page == 6}
	<Slide5 />
{/if}
