<script lang="ts">
</script>

<div class="page">
	<slot></slot>
</div>

<style lang="postcss">
	.page {
		@apply border-white border-2 rounded-3xl p-32 m-5 box-border flex flex-col gap-4 relative overflow-clip;
	}
</style>
