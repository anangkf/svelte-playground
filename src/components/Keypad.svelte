<script>
	import { createEventDispatcher } from 'svelte';

	export let value = '';

  const nums = [1,2,3,4,5,6,7,8,9];

	const dispatch = createEventDispatcher();

	const select = num => () => {
    if (value.length < 6) {
      value += num
    } else {
      alert('Max pin length is 6 chars')
    }
  };
  
	const clear  = () => value = '';
	const submit = () => dispatch('submit');
</script>

<div class="keypad">
  {#each nums as num, i (i)}
    <button on:click={select(num)}>{num}</button>
  {/each}

  <button disabled={!value} on:click={clear}>clear</button>
	<button on:click={select(0)}>0</button>
	<button disabled={!value} on:click={submit}>submit</button>
</div>

<style>
	.keypad {
		display: grid;
		grid-template-columns: repeat(3, 5em);
		grid-template-rows: repeat(4, 3em);
		grid-gap: 0.5em
	}

	button {
		margin: 0
	}
</style>