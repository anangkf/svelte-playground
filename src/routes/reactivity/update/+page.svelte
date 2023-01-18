<script>
  let nums = [1,2,3]
  let num;

  function addNumber(e){
    e.preventDefault()
    nums = [...nums, num]
    alert(`${num} added to the array!`)
    num = ''
  }
</script>

<svelte:head>
  <title>Reactivity Updates</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=VT323&display=swap" rel="stylesheet">
</svelte:head>

<section>
  <div class="flex-wrap column">
    <p class="display">{JSON.stringify(nums)}</p>
    <form on:submit={addNumber}>
      <input type="number" bind:value={num}>
      <button type="submit">Add number</button>
    </form>
  </div>
</section>

<style>
  .flex-wrap{
    display: flex;
    width: 98vw;
    height: 77vh;
    align-items: center;
    justify-content: center;
  }
  .column{
    flex-direction: column;
  }
  .display{
    font-family: 'VT323', monospace;
    font-weight: bold;
    font-size: 6rem;
  }
</style>