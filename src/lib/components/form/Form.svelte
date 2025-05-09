<script lang="ts">
	import type { Snippet } from 'svelte';
	import { applyAction, enhance } from '$app/forms';
	import { goto } from '$app/navigation';

	const { children }: { children: Snippet } = $props();
</script>

<form
	method="POST"
	use:enhance={({ formElement, formData, action, cancel }) => {
		return async ({ result }) => {
			// `result` is an `ActionResult` object
			if (result.type === 'redirect') {
				goto(result.location);
			} else {
				await applyAction(result);
			}
		};
	}}
>
	{@render children?.()}
</form>
