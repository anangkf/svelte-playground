<script>
  import {createEventDispatcher} from 'svelte'

  const dispatch = createEventDispatcher()
  function handlePress(){
    dispatch('press', {
      message: `Hi there! I'm passed from components event.`
    })
  }
</script>

<button on:click={handlePress}>Press me!</button>