<script lang="ts">
	import SlideCard from './SlideCard.svelte';
	import { page } from '$app/stores';

	let animate1 = false;

	console.log($page.url + 'video.mkv');
	setTimeout(() => {
		animate1 = true;
	}, 10);
</script>

<SlideCard>
	<h2
		class="{animate1
			? 'duration-700 opacity-100'
			: 'duration-200 opacity-0 translate-y-11'} absolute left-20 top-7 transition-all w-full"
	>
		Demo
	</h2>
	<iframe
		class="w-full h-full rounded-2xl bg-back"
		src="{$page.url}video.mkv"
		frameborder="0"
		title="video"
	></iframe>
</SlideCard>

<style lang="postcss">
	iframe {
		box-shadow: 0px 0px 50px 20px #000000;
	}
</style>
