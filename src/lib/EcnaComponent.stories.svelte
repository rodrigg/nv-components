<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import EcnaComponent from './EcnaComponent.svelte';

	// More on how to set up stories at: https://storybook.js.org/docs/writing-stories
	const { Story } = defineMeta({
		title: 'Example/EcnaComponent',
		component: EcnaComponent,
		argTypes: {
			texto: { control: 'color' },
			size: {
				control: { type: 'select' },
				options: ['`red`', 'blue']
			}
		},
		args: {}
	});
</script>

<!-- More on writing stories with args: https://storybook.js.org/docs/writing-stories/args -->
<Story name="Prueba" args={{ texto: 'Hola ECNA', color: 'red' }} />
