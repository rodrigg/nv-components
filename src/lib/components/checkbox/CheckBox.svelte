<script lang="ts">
	import type { IPropsInput } from '$lib/interfaces/IPropsInput';
	import InputContainer from '../InputContainer.svelte';

	let { value = $bindable(), ...props }: IPropsInput<boolean> = $props();
</script>

<InputContainer {...props} class={undefined} style="width: 99%;">
	<input type="checkbox" bind:value checked={value} name={props.name} />
</InputContainer>
