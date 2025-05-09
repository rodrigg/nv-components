<script lang="ts">
	import type { Snippet } from 'svelte';

	const { titulo, children }: { titulo: string; children: Snippet } = $props();
</script>

<div class="contenedor">
	<div class="titulo">{titulo}</div>
	<div>{@render children()}</div>
</div>

<style>
	.contenedor {
		display: flex;
		flex-direction: column;
	}
	.titulo {
		font-weight: bold;
		flex-grow: 1;
		background-color: gray;
		padding: 8px;
	}
</style>
