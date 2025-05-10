<svelte:options customElement="my-ecna" />

<script lang="ts">
	const { texto }: { texto: string } = $props();
</script>

<h1>{texto}</h1>
