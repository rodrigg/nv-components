<script lang="ts" generics="T">
	import type { Snippet } from 'svelte';

	let { data, header, row }: { data: T[]; header: Snippet; row: Snippet<[T, number]> } = $props();
</script>

<table>
	{#if header}
		<thead>
			<tr>{@render header()}</tr>
		</thead>
	{/if}

	<tbody>
		{#each data as d, index}
			<tr>{@render row(d, index)}</tr>
		{/each}
	</tbody>
</table>

<style>
	table {
		text-align: left;
		border-spacing: 0;
	}

	tbody tr:nth-child(2n + 1) {
		background: #eee;
	}

	table :global(th),
	table :global(td) {
		padding: 0.5em;
	}
</style>
