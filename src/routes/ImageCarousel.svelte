<script lang="ts">
	import ImageCard from './ImageCard.svelte';
	export let reversed: boolean = false;
	export let images: string[] = [];
	export let time: number = 42;
</script>

<div class="h-full w-full relative group">
	<div
		class="{reversed
			? 'carocel-rev'
			: 'carocel'} group-hover:pause absolute left-0 top-0 h-full w-full translate -translate-x-[calc(100%+12px)] gap-3 flex flex-row select-none"
		style="--time: {time}s;"
	>
		{#each images as src}
			<ImageCard {src} />
		{/each}
	</div>
	<div
		class="{reversed
			? 'carocel-rev'
			: 'carocel'} group-hover:pause absolute left-0 top-0 h-full w-full flex flex-row gap-3 select-none"
		style="--time: {time}s;"
	>
		{#each images as src}
			<ImageCard {src} />
		{/each}
	</div>
	<div
		class="{reversed
			? 'carocel-rev'
			: 'carocel'} group-hover:pause absolute left-0 top-0 h-full w-full translate-x-[calc(100%+12px)] gap-3 flex flex-row select-none"
		style="--time: {time}s;"
	>
		{#each images as src}
			<ImageCard {src} />
		{/each}
	</div>
</div>

<style lang="postcss">
	.carocel {
		animation: carocel var(--time) linear infinite;
	}
	.carocel-rev {
		animation: carocel var(--time) linear infinite reverse;
	}

	@keyframes carocel {
		from {
			left: 0%;
		}
		to {
			left: 101.5%;
		}
	}
</style>
