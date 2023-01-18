<script>
  let number = 0;
  $: doubled = number * 2;
  function increment(){
    number += 1
  }
</script>

<svelte:head>
  <title>Reactivity</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=VT323&display=swap" rel="stylesheet">
</svelte:head>

<section>
  <div class="flex-wrap column">
    <p class="num-display">{number}</p>
    <p>{number} doubled is {doubled}</p>
    <button class="increment-btn" on:click={increment}>Increment</button>
  </div>

</section>

<style>
  p{
    font-family: sans-serif;
  }
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
  .num-display{
    font-family: 'VT323', monospace;
    font-weight: bold;
    font-size: 6rem;
  }
  .increment-btn{
    background-color: #ffee48;
    padding: 1rem 2rem;
    font-size: medium;
    text-transform: uppercase;
    font-family: sans-serif;
    font-weight: 600;
    border: 3px solid #262329;
    border-radius: 14px;
    transition: ease-out .25s;
  }
  .increment-btn:hover{
    cursor: pointer;
    background-color: #ffdd48;
    transform: scale(1.075);
  }
</style>
