<script>
import JoinGame from './feedCards/JoinGame.svelte';
import OddsBoost from './feedCards/OddsBoost.svelte';
import PlaceBet from './feedCards/PlaceBet.svelte'
import PlayGame from './feedCards/PlayGame.svelte';
import PromotionCard from './feedCards/PromotionCard.svelte';
import TweetCard from './feedCards/TweetCard.svelte';
import WinBet from './feedCards/WinBet.svelte';

export let cardType = 'place_bet'

const feedCardClasses = ['feed-card']

$: if (cardType === 'win_bet') feedCardClasses.push('no-margin')
</script>

<article class={feedCardClasses.join(' ')}>
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
    --feed-card-padding: 16px;
  }

  .no-margin {
    --feed-card-padding: 0;
  }
  .feed-card {
  background-color: white;
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 5px;
  box-shadow: 2px 2px 2px rgba(0, 0, 0, 0.2);
  box-sizing: border-box;
  margin-bottom: 8px;
  padding: var(--feed-card-padding);
  max-width: 100%;
  width: 288px;
}
</style>
