<script>
	import Child from "../../components/Child.svelte";

  let passedValue

  function clear() {
    if(passedValue){
      passedValue = ''
    }
  }
  
</script>
<svelte:head>
  <title>Props</title>
</svelte:head>

<section>
  <p>We can pass a value to child components using props</p>
  <p>try changing input below</p>
  <input type="text" bind:value={passedValue}>
  <button on:click={clear}>Clear</button>
  <Child data={passedValue} />

  <a href="/props/spread">Coba permainan rangkai kata</a>
</section>

<style>
  a{
    text-decoration: none;
    color: #212121;
  }
  a:hover{
    color: #ff8811;
  }
</style>
