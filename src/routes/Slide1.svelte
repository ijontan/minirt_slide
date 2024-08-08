<script lang="ts">
	import SlideFirst from './SlideFirst.svelte';
	export let open: boolean;
	let animate1 = false;
	let animate2 = false;
	let animate3 = false;
	let timeout1: number | null = null;
	let timeout2: number | null = null;
	let timeout3: number | null = null;
	$: if (open) {
		timeout1 = setTimeout(() => {
			animate1 = true;
		}, 500);
		timeout2 = setTimeout(() => {
			animate2 = true;
		}, 1000);
		timeout3 = setTimeout(() => {
			animate3 = true;
		}, 2000);
	} else {
		if (timeout1) clearTimeout(timeout1);
		timeout1 = null;
		if (timeout2) clearTimeout(timeout2);
		timeout2 = null;
		if (timeout3) clearTimeout(timeout3);
		timeout3 = null;
		animate1 = false;
		animate2 = false;
		animate3 = false;
	}
</script>

<SlideFirst {open}>
	<h1
		class="{animate1 ? 'duration-1000' : 'opacity-0 translate-y-1/3 duration-200'} transition-all"
	>
		MiniRT
	</h1>
	<h2
		class="{animate2 ? 'duration-1000' : 'opacity-0 translate-y-1/3 duration-200'} transition-all"
	>
		A simple 3D Graphics Program
	</h2>
	<h3 class="{animate3 ? 'duration-[2500ms]' : 'opacity-0 duration-200'} transition-all">
		By: Ijon & Rong Jie
	</h3>
</SlideFirst>

<style lang="postcss">
</style>
