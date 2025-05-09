<script lang="ts">
	import InnerBoton from './InnerBoton.svelte';

	const { ...props }: { label?: string; icon?: 'plus' | 'erase' | 'check' } = $props();
</script>

<div class="contenedor">
	<button type="submit">
		<InnerBoton {...props} />
	</button>
</div>

<style>
	.contenedor {
		display: flex;
		justify-content: center;
		margin-top: 8px;
		padding: 8px;
		background-color: lightgrey;
	}
</style>
