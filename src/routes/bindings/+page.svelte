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

  let pref = '';
  let value = '';
  let year;
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
      <p>Career Preference in Web Development</p>
      <label>
        <input type="radio" bind:group={pref} name="pref" value="Frontend">
        Frontend
      </label><br>
      <label>
        <input type="radio" bind:group={pref} name="pref" value="Backend">
        Backend
      </label><br>
      <label>
        <input type="radio" bind:group={pref} name="pref" value="Fullstack">
        Fullstack
      </label><br>
      <label>
        <input type="radio" bind:group={pref} name="pref" value="DevOps">
        DevOps
      </label>
      <p>Write down your experience</p>
      <textarea cols="60" rows="10" bind:value /><br>
      <!-- <small>You can wrap the sentence with "*" to make them <em>italic</em> or "**" to make them <strong>bold</strong></small> -->
      <p>Experience (in year):</p>
      <select name="" bind:value={year} >
        {#each ['less than 1', '1 to 3', '3 to 5', 'more than 5'] as value }
          <option {value}>{value}</option>
        {/each}
      </select>
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
      <p>Prefered Role: {pref}</p>
      <p>Experience:</p>
      <p>{value}</p>
      <p>Experience (in year): {year} years</p>
    </aside>
  </section>
</main>

<style>
  .container{
    display: flex;
    justify-content: space-between;
    gap: 2rem;
    /* position: relative; */
  }
  .content{
    width: 40%;
    margin: 0 1rem;
  }
  .container aside{
    position: -webkit-sticky;
    position: sticky;
    top: 0;
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