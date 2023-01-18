<script>
  export let subjek = "S"
  export let predikat = "P"
  export let objek = "O"
  export let keterangan = "K"
</script>

<div>
  <p class="block">{subjek}</p>
  <p class="block">{predikat}</p>
  <p class="block">{objek}</p>
  <p class="block">{keterangan}</p>
</div>

<style>
  .block{
    background-color: #a1a1a1;
    display: inline;
    padding: 0 8px;
    border-radius: 2px;
  }
</style>