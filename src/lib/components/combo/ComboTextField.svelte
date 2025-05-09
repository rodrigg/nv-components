<script lang="ts">
	import type { ICodigoDescripcion } from '$lib/interfaces/ICodigoDescripcion';
	import type { IPropsInput } from '$lib/interfaces/IPropsInput';
	import TextField from '../textfield/TextField.svelte';
	import Combo from './Combo.svelte';

	let {
		lista,
		value = $bindable(),
		onChange
	}: { lista: ICodigoDescripcion[]; onChange: (valor: string | number | null) => void } & IPropsInput<string | null> = $props();

	function handleChangeTextField(event: any | null | undefined) {
		const localValue = event.currentTarget.value;
		const encontrado = lista.find((item) => item.codigo === localValue);
		if (encontrado) {
			onChange && onChange(event.target.value);
			value = localValue;
		}
	}
</script>

<div class="flex">
	<TextField class="col-1" bind:value onkeyup={(e) => handleChangeTextField(e)} />
	<Combo
		class="col-2"
		name="codigoModelo"
		{lista}
		bind:value
		onchange={(event: any) => onChange && onChange(event.target.value)}
	/>
</div>
