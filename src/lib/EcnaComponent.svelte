<svelte:options customElement="my-ecna" />

<script lang="ts">
	const {
		texto,
		color = 'black',
		size,
		subrayado
	}: { texto: string; color?: string; size: string; subrayado: string } = $props();

	const px = $derived(size === 'xs' ? '50px' : size === 'ms' ? '80px' : '120px');
</script>

<span style:color style:font-size={px} style:text-decoration={subrayado ? 'underline' : null}>
	{texto}
</span>
