<svelte:options customElement="my-ecna" />

<script lang="ts">
	const {
		texto,
		color = 'black',
		size,
		importante,
		parpadea
	}: {
		texto: string;
		color?: string;
		size: string;
		importante: boolean;
		parpadea: boolean;
	} = $props();

	const px = $derived(size === 'xs' ? '50px' : size === 'ms' ? '80px' : '120px');
</script>

<span class="btn" style:color class:importante class:parpadea style:font-size={px}>
	{texto}
</span>

<style>
	.importante {
		font-weight: 700;
		text-decoration: underline;
	}
	.parpadea {
		animation: blink 0.8s steps(2, start) infinite;
	}

	@keyframes blink {
		to {
			visibility: hidden;
		}
	}
</style>
