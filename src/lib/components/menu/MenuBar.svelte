<script lang="ts">
	import type { IMenuBar } from '$lib/interfaces/IMenuBar';
	const { listaMenus }: { listaMenus: IMenuBar[] } = $props();
</script>

<ul>
	{#each listaMenus as itemMenu}
		<li>
			<a href={itemMenu.url}> {itemMenu.descCas}</a>
			<ul>
				{#each itemMenu.children || [] as itemChildren}
					<li>
						<a href={`${itemMenu.url}${itemChildren.url}`}> {itemChildren.descCas}</a>
					</li>
				{/each}
			</ul>
		</li>
	{/each}
</ul>
