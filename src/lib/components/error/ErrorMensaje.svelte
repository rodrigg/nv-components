<script lang="ts">
	const { mensaje } = $props();
</script>

{#if mensaje}
	<div class="container">{mensaje}</div>
{/if}

<style>
	.container {
		border: 1px solid red;
		padding: 8px;
		color: red;
	}
</style>
