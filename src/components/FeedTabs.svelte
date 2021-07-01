<script>
export let active = 'feed'

const setActive = newTab => active = newTab
</script>

<nav class="tabs font-body-1">
  <div
    class={active === 'feed' ? 'active' : ''}
    on:click={() => setActive('feed')}>
    My Feed
  </div>

  <div
    class={active === 'teams' ? 'active' : ''}
    on:click={() => setActive('teams')}>
    My Teams
  </div>

  <div
    class={active === 'friends' ? 'active' : ''}
    on:click={() => setActive('friends')}>
    Friends
  </div>
</nav>

<style>
  .tabs {
    color: gray;
    cursor: pointer;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    text-align: center;
    transition: all 300ms
  }

  .tabs > * {
    padding: 8px 0;
  }

  .active {
    box-shadow: inset 0 -3px red;
    color: white;
    transition: all 300ms
  }
</style>