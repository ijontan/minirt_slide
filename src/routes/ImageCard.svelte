<script lang="ts">
	export let src: string = '';
	export let alt: string = '';
	const appearTime = Math.floor(Math.random() * 2000);
	let animate1 = false;
	setTimeout(() => {
		animate1 = true;
	}, appearTime);
</script>

<img
	class="{animate1
		? 'duration-700 opacity-80 hover:opacity-100'
		: 'opacity-0 duration-100'} h-full flex-1 min-w-0 transition-all border-white border-2 rounded-xl"
	{src}
	{alt}
/>
