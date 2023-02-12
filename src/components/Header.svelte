<script>
  import { page } from '$app/stores';

  const routes = [
    {id: 1, label: 'Reactivity', path: '/reactivity'},
    {id: 2, label: 'Props', path: '/props'},
    {id: 3, label: 'Logic', path: '/logic'},
    {id: 4, label: 'Events', path: '/events'},
    {id: 5, label: 'Bindings', path: '/bindings'},
  ]
  
</script>

<nav>
  <ul>
    <li 
        class:active={$page.url.pathname === '/'}
      >
        <a href='/'>Intro</a>
      </li>
    <!-- keyed each -->
    {#each routes as {id, label, path} (id)}
      <li 
        class:active={$page.url.pathname.includes(path)}
      >
        <a href={path}>{label}</a>
      </li>
    {/each}
  </ul>
  <hr>
</nav>

<style>
  ul{
    display: flex;
    gap: 16px;
    margin-bottom: 0px;
    padding: 0;
  }
  ul li {
    list-style: none;
    display: inline;
  }
  ul li a{
    text-decoration: none;
    color: #212121;
  }
  ul li:not(.active):hover a{
    color: #ff8811;
  }
  hr{
    border: 1px solid #aaffee;
  }
  .active{
    background-color: #ff8811;
    padding: 0 3px;
    border-radius: 2px;
  }
</style>