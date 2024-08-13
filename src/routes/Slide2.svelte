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
		Project Scope
	</h1>
	<ul
		class="{animate2
			? 'duration-700'
			: ' duration-200 opacity-0 translate-y-11'} list-disc list-inside transition-all flex flex-col gap-8"
	>
		<li>Rendering a 3D objects and scenes.</li>
		<li>Manipulating the objects in realtime</li>
		<li>Moving around the scene</li>
		<li>No external libraries allow other than minilibx.</li>
	</ul>
	<AnimationBlock positionClass="top-[-500px] left-[-440px]" size={1000} speed={36} clockwise />
	<AnimationBlock positionClass="bottom-[-300px] left-[50px]" size={600} speed={24} />
	<AnimationBlock positionClass="top-[-100px] right-[-120px]" size={500} speed={30} />
	<AnimationBlock positionClass="bottom-[-500px] right-[-440px]" size={1000} speed={40} />
</SlideCard>
