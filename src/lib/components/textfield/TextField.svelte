<script lang="ts">
	import type { IPropsInput } from '$lib/interfaces/IPropsInput';
	import InputContainer from '../InputContainer.svelte';

	let { value = $bindable(), ...props }: IPropsInput<string | null> = $props();
</script>

<InputContainer {...props}>
	<input bind:value {...props} class={undefined} style="width: 100%;" />
</InputContainer>
