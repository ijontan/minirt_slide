<script lang="ts">
	import AnimationBlock from './AnimationBlock.svelte';
	import ImageCarousel from './ImageCarousel.svelte';
	import SlideCard from './SlideCard.svelte';
	import cg from '$lib/images/cg.jpg';
	import medical from '$lib/images/medical.jpg';
	import arvr from '$lib/images/arvr.jpg';
	import edu from '$lib/images/edu.jpeg';
	let animate1 = false;
	let animate2 = false;
	setTimeout(() => {
		animate1 = true;
	}, 10);
	setTimeout(() => {
		animate2 = true;
	}, 500);
</script>

<SlideCard>
	<h1
		class="{animate1
			? 'duration-700'
			: 'duration-200 opacity-0 translate-y-11'} transition-all mb-20 text-8xl w-full"
	>
		Real World Applications
	</h1>
	<ul
		class="{animate2
			? 'duration-700'
			: ' duration-200 opacity-0 translate-y-11'} list-disc list-inside transition-all flex flex-col gap-8
			mb-20
		"
	>
		<li>Computer Graphics, Animation, Game Development</li>
		<li>Visualization of various field: medical, architectural, scientific, etc</li>
		<li>VR and AR</li>
		<li>Education and Training</li>
	</ul>
	<ImageCarousel time={60} images={[cg, medical, arvr, edu]} />
	<AnimationBlock positionClass="top-[-500px] left-[-440px]" size={1000} speed={36} clockwise />
	<AnimationBlock positionClass="bottom-[-500px] right-[-440px]" size={1500} speed={40} />
</SlideCard>
