<script lang="ts">
	import InnerBoton from './InnerBoton.svelte';

	const {
		onclick,
		class: classProp = 'primary',
		...props
	}: {
		label?: string;
		onclick: (event: MouseEvent & { currentTarget: EventTarget & HTMLButtonElement }) => void;
		icon?: 'plus' | 'erase' | 'check';
		class?: string;
	} = $props();

	function handleClicK(event: MouseEvent & { currentTarget: EventTarget & HTMLButtonElement }) {
		event.preventDefault();
		onclick(event);
	}
</script>

<div class="contenedor">
	<button onclick={handleClicK}>
		<InnerBoton {...props} />
	</button>
</div>

<style>
	.contenedor {
		padding: 8px;
		align-self: flex-end;
	}
</style>
