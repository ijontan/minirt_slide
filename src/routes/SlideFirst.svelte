<script lang="ts">
	export let open: boolean;
</script>

<div
	class="page {open
		? 'w-[calc(100vw-40px)] h-[calc(100vh-40px)]'
		: ' w-20 h-20 bg-main rotate-[135deg] translate-x-[calc(50vw-60px)] translate-y-[calc(50vh-60px)]'}"
>
	<slot></slot>
</div>

<style lang="postcss">
	.page {
		@apply border-white border-2 rounded-3xl p-5 m-5 box-border flex flex-col items-center content-center justify-center transition-all duration-500;
	}
</style>
