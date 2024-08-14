<script lang="ts">
	import ImageCarousel from './ImageCarousel.svelte';
	import SlideCard from './SlideCard.svelte';
	import coloredBall from '$lib/images/coloredBall.webp';
	import ball1 from '$lib/images/balls1.png';
	import ball2 from '$lib/images/balls2.png';
	import coloredMBall from '$lib/images/coloredmetalball.webp';
	import metalBall from '$lib/images/metalball.webp';
	import metals from '$lib/images/metals.webp';
	import metal1 from '$lib/images/metal2.png';
	import metal2 from '$lib/images/metal3.png';
	import earth from '$lib/images/earth.webp';
	import msia from '$lib/images/msia.png';
	import scene1 from '$lib/images/scene2.png';
	import scene2 from '$lib/images/scene22.png';

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
	<ImageCarousel time={60} images={[coloredBall, coloredMBall, ball2, metalBall]} />
	<ImageCarousel time={60} images={[scene2, ball1, metal2, msia]} reversed />
	<ImageCarousel time={70} images={[scene1, metal1, metals, earth]} />
</SlideCard>
