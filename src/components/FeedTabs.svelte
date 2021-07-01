<script>
export let active = 'feed'
</script>

<nav class="font-body-2">
  <div class={active === 'feed' ?? 'active'}>My Feed</div>
  <div class={active === 'teams' ?? 'active'}>My Teams</div>
  <div class={active === 'friends' ?? 'active'}>Friends</div>
</nav>
