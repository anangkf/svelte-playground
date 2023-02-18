<script>
	import Keypad from '../../../components/Keypad.svelte';

	let pin;
	$: view = pin ? pin.replace(/\d(?!$)/g, '•') : 'enter your pin';
  
	function handleSubmit() {
		alert(`submitted ${pin}`);
	}
  
</script>

<svelte:head>
  <title>Create Pin</title>
</svelte:head>

<main>
  <h1 style="color: {pin ? '#333' : '#ccc'}">{view}</h1>
  <small>maximum 6 characters</small>
  
  <Keypad bind:value={pin} on:submit={handleSubmit}/>
</main>