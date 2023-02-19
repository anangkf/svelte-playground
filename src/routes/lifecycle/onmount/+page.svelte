<script>
  import { onMount } from 'svelte'

	let photos = [];
  
  onMount(async () => {
    const res = await fetch('https://picsum.photos/v2/list?limit=10');
		photos = await res.json();
  })
</script>
 
<svelte:head>
  <title>Lifecycle: onMount</title> 
</svelte:head>

<main>
  <h1>Photo album</h1>

  <div class="photos">
    {#each photos as photo (photo.id)}
      <figure>
        <img src={photo.url} alt={photo.title}>
        <figcaption>{photo.author}</figcaption>
      </figure>
    {:else}
      <!-- this block renders when photos.length === 0 -->
      <p>loading...</p>
    {/each}
  </div>
</main>

<style>
	.photos {
		width: 100%;
		display: grid;
		grid-template-columns: repeat(5, 1fr);
		grid-gap: 8px;
	}

	figure, img {
		width: 100%;
		margin: 0;
	}
</style>