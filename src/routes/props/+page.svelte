<script>
	import Child from "../../components/Child.svelte";

  let passedValue

  function clear() {
    if(passedValue){
      passedValue = ''
    }
  }
  
</script>

<section>
  <p>We can pass a value to child components using props</p>
  <p>try changing input below</p>
  <input type="text" bind:value={passedValue}>
  <button on:click={clear}>Clear</button>
  <Child data={passedValue} />
</section>