<script lang="ts">
	import AnimationBlock from './AnimationBlock.svelte';
	import SlideCard from './SlideCard.svelte';
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
		Things we learned
	</h1>
	<ul
		class="{animate2
			? 'duration-700'
			: ' duration-200 opacity-0 translate-y-11'} list-disc list-inside transition-all flex flex-col gap-8"
	>
		<li>Mathematical equations for various shape.</li>
		<li>
			Rendering techniques: Phong Illumination Model, Ray Tracing, UV mapping, Randering Equations.
		</li>
		<li>Material characteristic in different conditions.</li>
		<li>Working with Graphic library</li>
	</ul>
	<AnimationBlock positionClass="top-[-50px] left-[-100px]" size={1200} speed={50} clockwise />
</SlideCard>
