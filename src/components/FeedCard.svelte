<script>
import PlaceBet from './feedCards/PlaceBet.svelte'

export let cardType = 'placeBet'
</script>

<article class="feed-card">
  {#if cardType === 'placeBet'}
    <PlaceBet />
  {/if}
</article>

<style>
.feed-card {
  background-color: white;
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 5px;
  box-shadow: 2px 2px 2px rgba(0, 0, 0, 0.2);
  padding: 20px;
  max-width: 100%;
  width: 420px;
}
</style>
