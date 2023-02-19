<script>
  import { page } from '$app/stores';
  import { goto } from '$app/navigation'

  const routes = [
    {id: 1, label: 'Reactivity', type: 'link', path: '/reactivity'},
    {id: 2, label: 'Props', type: 'link', path: '/props'},
    {id: 3, label: 'Logic', type: 'link', path: '/logic'},
    {id: 4, label: 'Events', type: 'link', path: '/events'},
    {id: 5, label: 'Bindings', type: 'link', path: '/bindings'},
    {
      id: 6, 
      label: 'Lifecycle', 
      type: 'dropdown', 
      child: [
        {id: 61, label: 'onMount', path: '/lifecycle/onmount'},
        {id: 62, label: 'onDestroy', path: '/lifecycle/ondestroy'},
        {id: 63, label: 'beforeUpdate & afterUpdate', path: '/lifecycle/update'},
        {id: 64, label: 'tick', path: '/lifecycle/tick'},
      ]
    }
  ]

  let selectedPath;
  
</script>

<nav>
  <ul>
    <li 
        class:active={$page.url.pathname === '/'}
      >
        <a href='/'>Intro</a>
      </li>
    <!-- keyed each -->
    {#each routes as {id, label, type, path, child} (id)}
      {#if type === 'dropdown'}
        <select class="dropdown" bind:value={selectedPath} on:change={() => goto(selectedPath)}>
          <option value="/">Lifecycle</option>
          {#each child as {id, label, path} (id) }
            <option 
              value={path}
              class:active={$page.url.pathname.includes(path)}
            >
              {label}
            </option>
          {/each}
        </select>
      {:else}
        <li 
          class:active={$page.url.pathname.includes(path)}
        >
          <a href={path}>{label}</a>
        </li>
      {/if}
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
  .dropdown{
    width: 6rem;
  }
</style>