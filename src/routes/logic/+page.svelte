<script>
  let number;
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