<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import Something from './Something.svelte';

	// More on how to set up stories at: https://storybook.js.org/docs/writing-stories
	const { Story } = defineMeta({
		title: 'Example/Something',
		component: Something,
		tags: ['autodocs'],
		argTypes: {},
		args: {}
	});
</script>

<!-- More on writing stories with args: https://storybook.js.org/docs/writing-stories/args -->
<Story name="prueba" />
