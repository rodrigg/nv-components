<script lang="ts">
	import type { IPropsInput } from '$lib/interfaces/IPropsInput';
	import type { Component, Snippet } from 'svelte';
	const props = $props();
	const { label, class: classProp, children, name }: { children: Snippet } & Omit<IPropsInput<unknown>, 'value'> = props;
</script>

<div class={`${classProp}`}>
	<label for={name}>{label}</label>
	{@render children()}
</div>
