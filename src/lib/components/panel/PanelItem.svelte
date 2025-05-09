<script lang="ts">
	import type { Snippet } from 'svelte';

	const { children, label }: { label: string; children: Snippet } = $props();
</script>

<div class="contenedor">
	<div class="label">{label}</div>
	<div class="component">{@render children?.()}</div>
</div>

<style>
	.contenedor {
		display: flex;
	}
	.label {
		flex: 1 !important;
		padding: 8px;
		background-color: gray;
	}
	.component {
		flex: 5 !important;
		background-color: lightgray;
		padding-left: 8px;
	}
</style>
