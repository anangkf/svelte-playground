<script>
  let number;

  const todos = [
    {
        id: 1,
        title: "Clean the kitchen",
        description: "Mop the floor, wipe the countertop and don't forget to take out the trash!"
    },
    {
        id: 2,
        title: "Call Mom",
        description: "It's her birthday!"
    },
    {
        id: 3,
        title: "Water flowers",
        description: "They need water, or they will die."
    }
  ]

</script>

<svelte:head>
  <title>Logic</title>
</svelte:head>

<section>
  <input type="number" bind:value={number}>
  <p>Angka yang Anda masukkan adalah bilangan
    {#if number % 2 === 0}
      genap
    {:else}
      ganjil
    {/if}
  </p>
</section>

<section>
  <h3>Todos</h3>
  {#each todos as {id, title, description}, i }
    <div class="todo-item">
      <header>{i+1}. {title}</header>
      <details>{description}</details>
    </div>
  {/each}
</section>

<style>
  .todo-item{
    margin: 10px 0;
  }
</style>