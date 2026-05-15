<svelte:options customElement="my-ecna" />

<script lang="ts">
	const {
		texto,
		color = 'black',
		size,
		importante,
		parpadea,
		aparece
	}: {
		texto: string;
		color?: string;
		size: string;
		importante: boolean;
		parpadea: boolean;
		aparece?: boolean;
	} = $props();

	const px = $derived(size === 'xs' ? '50px' : size === 'ms' ? '80px' : '130px');
</script>

<span class="btn" class:aparece style:color class:importante class:parpadea style:font-size={px}>
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

	.aparece {
		position: absolute;
		width: 300px;
		height: 300px;
		background: radial-gradient(circle, rgba(168, 85, 247, 0.5), transparent 70%);
		top: -10px;
		left: 0px;
		animation: float 6s ease-in-out infinite;
	}

	@keyframes gradientMove {
		0% {
			background-position: 0%;
		}
		100% {
			background-position: 300%;
		}
	}

	@keyframes float {
		0%,
		100% {
			transform: translate(0, 0);
		}
		50% {
			transform: translate(40px, 30px);
		}
	}
</style>
