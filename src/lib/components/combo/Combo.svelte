<script lang="ts">
	import type { ICodigoDescripcion } from '$lib/interfaces/ICodigoDescripcion';
	import type { IPropsInput } from '$lib/interfaces/IPropsInput';
	import InputContainer from '../InputContainer.svelte';

	let { lista, value = $bindable(), ...props }: { lista: ICodigoDescripcion[] } & IPropsInput<string | null> = $props();
</script>

<InputContainer {...props}>
	<select bind:value {...props} class={undefined} style="width: 100%;">
		{#each lista as item}
			<option value={item.codigo}>{item.desCas}</option>
		{/each}
	</select>
</InputContainer>
