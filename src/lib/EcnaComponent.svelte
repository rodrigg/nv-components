<svelte:options customElement="my-ecna" />

<script lang="ts">
	const { texto, color }: { texto: string; color?: string } = $props();
</script>

<h1 style:color>{texto}</h1>
