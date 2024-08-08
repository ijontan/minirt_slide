<script lang="ts">
	const appearTime = Math.floor(Math.random() * 2000);
	const startDeg = -Math.floor(Math.random() * 360);
	export let size = 200;
	export let speed = 4;
	export let positionClass: string = 'left-0 right-0';
	export let clockwise: boolean = false;
	let animate1 = false;
	setTimeout(() => {
		animate1 = true;
	}, appearTime);
</script>

<div
	class="{animate1
		? 'duration-700 opacity-30'
		: 'duration-200 opacity-0'} transition-all absolute -z-10 {positionClass} border-white border-2 my-spin bg-main-dark"
	style="--start-deg: {startDeg}deg; --size: {size}px; --speed: {speed}s; --rotate:{clockwise
		? 360
		: -360}deg"
></div>

<style lang="postcss">
	.my-spin {
		animation: spin var(--speed) cubic-bezier(0.445, 0.05, 0.55, 0.95) infinite;
		width: var(--size);
		height: var(--size);
	}
	@keyframes spin {
		0% {
			border-radius: calc(var(--size) / 6);
			transform: rotate(var(--start-deg));
		}
		50% {
			border-radius: calc(var(--size) * 3 / 7);
		}
		100% {
			border-radius: calc(var(--size) / 6);
			transform: rotate(calc(var(--start-deg) + var(--rotate)));
		}
	}
</style>
