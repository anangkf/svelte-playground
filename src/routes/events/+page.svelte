<script>
  let m ={ x: 0, y: 0}

  function handleMouseMove(e){
    const {x, y} = e
    m.x = x;
    m.y = y;
  }
</script>

<section class="screen" on:mousemove={handleMouseMove}>
  <h3>The mouse position is: {m.x} x {m.y} </h3>
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