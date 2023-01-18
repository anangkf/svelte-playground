<script>
  let number = 0;
  $: doubled = number * 2;
  function increment(){
    number += 1
  }
  function reset(){
    number = 0
  }
  // You can easily group statements together with a block:
  $: {
    console.log(`the count is ${number}`)
    // alert(`number incremented succesfully!`)
  }
  // You can even put the $: in front of things like if blocks:
  $: {
    if(number > 20){
      alert(`The number is too much! \nwe are going to reset it.`)
      reset()
    }
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
    <div class="flex-wrap gap">
      <button class="btn increment-btn" on:click={increment}>Increment</button>
      <button class="btn reset-btn" on:click={reset}>Reset</button>
    </div>
    <a href="/reactivity/update">Check update feature out!</a>
  </div>

</section>

<style>
  p{
    font-family: sans-serif;
  }
  a{
    text-decoration: none;
    color: #212121;
  }
  a:hover{
    color: #ff8811;
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
  .btn{
    padding: 1rem 2rem;
    font-size: medium;
    text-transform: uppercase;
    font-family: sans-serif;
    font-weight: 600;
    border: 3px solid #262329;
    border-radius: 14px;
    transition: ease-out .25s;
  }
  .btn:hover{
    cursor: pointer;
    transform: scale(1.075);
  }
  .increment-btn{
    background-color: #ffee48;
  }
  .increment-btn:hover{
    background-color: #ffdd48;
  }
  .reset-btn{
    background-color: #ff2233;
  }
  .reset-btn:hover{
    background-color: #ff2020;
  }
  .gap{
    gap: 12px;
  }
</style>
