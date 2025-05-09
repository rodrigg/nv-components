<script lang="ts">
	import plussvg from '../icons/plus.svg';
	import eraseSvg from '../icons/erase.svg';
	import checkSvg from '../icons/check.svg';

	const { icon, style }: { icon: 'plus' | 'erase' | 'check'; style?: any } = $props();
	const icons = { plus: plussvg, erase: eraseSvg, check: checkSvg };
</script>

<img src={icons[icon]} alt="" {style} />
