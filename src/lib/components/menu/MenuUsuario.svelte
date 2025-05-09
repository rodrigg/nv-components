<script lang="ts">
	import type { IUser } from '$lib/interfaces/IUser';
	const { usuario }: { usuario: IUser } = $props();
</script>

<div>{usuario?.nombre}</div>
<div>{usuario?.apellidos}</div>
