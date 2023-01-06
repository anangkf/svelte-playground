<script>
  import Child from '../components/Child.svelte'
  let name='world'
  let randomImg = 'https://scontent.fjog9-1.fna.fbcdn.net/v/t1.6435-9/180978949_314228950059549_1005358403722529104_n.jpg?_nc_cat=105&ccb=1-7&_nc_sid=09cbfe&_nc_eui2=AeEWVbxRvnLB9g7w89jhvl2QIUR2JKXD5MAhRHYkpcPkwFX5syMpMwgZkvRlOQai4-TJLB1XMO759TMCyHrttnUa&_nc_ohc=PPDb9BF8iYAAX97DeqF&_nc_ht=scontent.fjog9-1.fna&oh=00_AfCHvvmD_GbMp_Gi6bEDllgFWOUnPL1M9CocDJAuPMmb2w&oe=63DF3A4E'
</script>

<h1>Welcome to SvelteKit</h1>
<p>Hello {name}!</p>
<img class="image" src={randomImg} aria-hidden="true" alt="random-image">
<Child data={'lorem ipsum dolor sit amet'}/>

<style>
  .image{
    width: 200px;
    border: 2px dotted #edaa66;
  }
</style>