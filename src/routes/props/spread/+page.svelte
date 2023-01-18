<script>
	import RangkaiKata from "../../../components/RangkaiKata.svelte";
  const data ={
    subjek: 'S',
    predikat: 'P',
    objek: 'O',
    keterangan: 'K',
  }
  
</script>

<svelte:head>
  <title>Spread Props</title>
</svelte:head>

<section>
  <RangkaiKata {...data}/>

  <p>Kamu dapat mengubah kalimat diatas dengan mengisi form dibawah</p>
  <label for="subjek">
    subjek
  </label><br>
  <input type="text" id="subjek" bind:value={data.subjek}><br>
  <label for="predikat">
    predikat
  </label><br>
  <input type="text" id="predikat" bind:value={data.predikat}><br>
  <label for="objek">
    objek
  </label><br>
  <input type="text" id="objek" bind:value={data.objek}><br>
  <label for="keterangan">
    keterangan
  </label><br>
  <input type="text" id="keterangan" bind:value={data.keterangan}>
</section>