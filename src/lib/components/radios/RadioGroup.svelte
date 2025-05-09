<script lang="ts">
	import type { IPropsInput } from '$lib/interfaces/IPropsInput';
	import Icon from '../icons/Icon.svelte';
	import InputContainer from '../InputContainer.svelte';

	let { valorDefecto, value = $bindable(), ...props }: IPropsInput<string | null> & { valorDefecto: string } = $props();
	function handleChange(event: any) {
		value = event.target?.value;
	}
</script>

{#if valorDefecto === value}
	<Icon icon="check" />
	<input type="hidden" name={props.name} {value} />
{:else if !value}
	<InputContainer {...props} class={undefined} style="width: 99%;">
		<input type="radio" onchange={(e) => handleChange(e)} {...props} value={valorDefecto} />
	</InputContainer>
{/if}
