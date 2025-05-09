<script lang="ts">
	import type { IPropsInput } from '$lib/interfaces/IPropsInput';
	import InputContainer from '../InputContainer.svelte';

	let { value = $bindable(), ...props }: IPropsInput<Date | null> = $props();
</script>

<InputContainer {...props}>
	<input type="date" bind:value name={props.name} class={undefined} style="width: 100%;" />
</InputContainer>
