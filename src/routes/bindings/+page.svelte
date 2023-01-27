<script>
  let name = '';
  let age = '';

  const languages = [
    {key: 'javascript', name: 'Javascript'},
    {key: 'react', name: 'React'},
    {key: 'vue', name: 'Vue'},
    {key: 'angular', name: 'Angular'},
    {key: 'svelte', name: 'Svelte'},
    {key: 'astro', name: 'Astro'},
    {key: 'solidjs', name: 'Solidjs'},
    {key: 'nextjs', name: 'Nextjs'},
    {key: 'nuxtjs', name: 'Nuxtjs'},
  ]

  // $: exps = []
  let exps = []
  
  function addExp(name){
    exps = [...exps, name]
  }

</script>

<svelte:head>
  <title>Bindings</title>
</svelte:head>

<main>
  <section class="container">
    <form class="content">
      <h2>Form Registration Sveltekit Crashcourse 2023</h2>
      <label class="formparts" for="name">
        Name: 
        <input type="text" bind:value={name} name="name" id="name">
      </label><br>
      <label class="formparts" for="age">
        Age: 
        <input type="number" bind:value={age} name="age" id="age">
      </label>
      <p>Which Language/Framework you've experienced in:</p>
      <div class="explang">
        {#each languages as {key, name} }
          <label for={key}>
            <input type="checkbox" id={key} on:change={() => addExp(name)}>
            {name}
          </label>
        {/each}
      </div>
    </form>
    <aside class="content">
      <h2>Your data</h2>
      <p>Name: {name}</p>
      <p>Age: {age}</p>
      <p>Experienced Languages or Frameworks:</p>
      <ol>
        {#each exps as exp}
          <li>{exp}</li>
        {/each}
      </ol>
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
  .formparts{
    display: grid;
    grid-template-columns: 1fr 3fr;
  }
  .explang{
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(12rem, 1fr));
  }
</style>