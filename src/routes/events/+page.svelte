<!-- The full list of modifiers:
  preventDefault eq event.preventDefault()
  stopPropagation eq event.stopPropagation()
  passive | improves scrolling performance on touch/wheel events (Svelte will add it automatically where it's safe to do so)
  nonpassive | explicitly set passive: false
  capture | fires the handler during the capture phase instead of the bubbling phase (MDN docs)
  once | remove the handler after the first time it runs
  self | only trigger handler if event.target is the element itself
  trusted | only trigger handler if event.isTrusted is true. I.e. if the event is triggered by a user action.
-->
<script>
	import Inner from "../../components/Inner.svelte";

  const INIT_MOUSE_POSITION = { x: 0, y: 0};
  // if we not spread INIT_MOUSE_POSITION both m and INIT_MOUSE_POSITION values will be changed
  let m = {...INIT_MOUSE_POSITION}

  function handleMouseMove(e){
    const {x, y} = e
    m.x = x;
    m.y = y;
  }

  function handleReset(){
    m = INIT_MOUSE_POSITION
  }

  function handlePress(e){
    const {message} = e.detail
    alert(message)
  }
</script>

<svelte:head>
  <title>Events</title>
</svelte:head>

<!-- we can add inline event handler like this
<section class="screen" on:mousemove="{e => m = {x: e.x, y: e.y}}"> -->
<section class="screen" on:mousemove={handleMouseMove}>
  <h3>The mouse position is: {m.x} x {m.y} </h3>
  <!-- we use event modifier here -->
  <!-- we can also chaining event modifiers together -->
  <!-- <button on:click|once|preventDefault={handleReset}>Reset once</button> -->
  <button on:click|once={handleReset}>Reset once</button>
  <Inner on:press={handlePress}/>
</section>

<style>
  .screen{
    height: 80vh;
    width: 98.7vw;
    background-color: #ededaa;
    margin: 0;
  }
  h3{
    margin: 0;
  }
</style>