<script>
  let name = '';
  let age = '';
</script>

<svelte:head>
  <title>Bindings</title>
</svelte:head>

<main>
  <section class="container">
    <form class="content">
      <h2>Form Registration Sveltekit Crashcourse 2023</h2>
      <label for="name">
        Name: 
        <input type="text" bind:value={name} name="name">
      </label><br>
      <label for="age">
        Age: 
        <input type="number" bind:value={age} name="age">
      </label>
    </form>
    <aside class="content">
      <h2>Your data</h2>
      <p>Name: {name}</p>
      <p>Age: {age}</p>
    </aside>
  </section>
</main>

<style>
  .container{
    display: flex;
    justify-content: space-between;
    gap: 2rem;
  }
  .content{
    width: 40%;
    margin: 0 1rem;
  }
  label{
    display: grid;
    grid-template-columns: 1fr 3fr;
  }
</style>