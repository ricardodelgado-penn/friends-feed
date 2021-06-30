<script>
import JoinGame from './feedCards/JoinGame.svelte';
import OddsBoost from './feedCards/OddsBoost.svelte';
import PlaceBet from './feedCards/PlaceBet.svelte'
import PlayGame from './feedCards/PlayGame.svelte';
import PromotionCard from './feedCards/PromotionCard.svelte';
import TweetCard from './feedCards/TweetCard.svelte';
import WinBet from './feedCards/WinBet.svelte';

export let cardType = 'place_bet'
</script>

<article class="feed-card">
  {#if cardType === 'place_bet'}
    <PlaceBet />
  {/if}

  {#if cardType === 'win_bet'}
    <WinBet />
  {/if}

  {#if cardType === 'play_game'}
    <PlayGame />
  {/if}

  {#if cardType === 'join_game'}
    <JoinGame />
  {/if}

  {#if cardType === 'odds_boost'}
    <OddsBoost />
  {/if}

  {#if cardType === 'promotion'}
    <PromotionCard />
  {/if}

  {#if cardType === 'tweet'}
    <TweetCard />
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
