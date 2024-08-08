<script lang="ts">
	import ImageCarousel from './ImageCarousel.svelte';
	import SlideCard from './SlideCard.svelte';
	import coloredBall from '$lib/images/coloredBall.webp';
	import coloredMBall from '$lib/images/coloredmetalball.webp';
	import metalBall from '$lib/images/metalball.webp';
	import metals from '$lib/images/metals.webp';
	import earth from '$lib/images/earth.webp';
	let animate1 = false;
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
		Gallery
	</h2>
	<ImageCarousel time={60} images={[coloredBall, coloredMBall, earth, metalBall]} />
	<ImageCarousel time={60} images={[metals, earth, coloredBall, coloredMBall]} reversed />
	<ImageCarousel time={70} images={[metalBall, coloredBall, metals, earth]} />
</SlideCard>
