<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import EcnaComponent from './EcnaComponent.svelte';

	// More on how to set up stories at:
	const { Story } = defineMeta({
		title: 'Example/EcnaComponent',
		component: EcnaComponent,
		argTypes: {
			texto: { control: 'color' },
			size: {
				control: { type: 'select' },
				options: ['xs', 'ms', 'ls']
			},
			parpadea: { control: { type: 'boolean' } },
			importante: { control: { type: 'boolean' } },
			aparece: { control: { type: 'boolean' } }
		},
		args: {}
	});
</script>

<!-- More on writing stories with args: https://storybook.js.org/docs/writing-stories/args -->
<Story name="Prueba" args={{ texto: 'Hola ECNA', color: 'red' }} />
<Story name="Prueba2" args={{ texto: 'Hola Ecnayuno', color: 'blue', aparece: true }} />
