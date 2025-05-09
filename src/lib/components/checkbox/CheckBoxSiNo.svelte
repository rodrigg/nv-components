<script lang="ts">
	import type { IPropsInput } from '$lib/interfaces/IPropsInput';
	import InputContainer from '../InputContainer.svelte';
	let { value = $bindable(), ...props }: IPropsInput<boolean | null > = $props();
// Variable que determina si el checkbox es habilitado

	function toggleCheckbox(e:any ,sino:"si"|"no") {
		let checkedLocal=e.target.checked
		if(sino==="si" && checkedLocal){
			value=true
		}else if(sino==="no" && checkedLocal){
			value=false
		}
		else{
			value=null;
		}
	
	}

</script>


<InputContainer {...props}>
	<input type="checkbox" name="Si" onchange={(e)=> toggleCheckbox(e,"si")}  checked={value===true}/>
	Si
	<input type="checkbox" name="No"   onchange={(e)=> toggleCheckbox(e,"no")} checked={value===false} >
	No
</InputContainer>
