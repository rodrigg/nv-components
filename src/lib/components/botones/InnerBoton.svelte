<script lang="ts">
	import Icon from '../icons/Icon.svelte';

	const { label, icon }: { label?: string; icon?: 'plus' | 'erase' | 'check'; class?: string } = $props();
</script>

<div class="inner-boton">
	{#if icon}
		<Icon {icon} style="{label ? 'padding-right : 8px;' : undefined}}" />
	{/if}

	{#if label}
		<div>{label}</div>
	{/if}
</div>

<style>
	.inner-boton {
		display: flex;
		align-items: center;
		padding: 4px;
	}
</style>
