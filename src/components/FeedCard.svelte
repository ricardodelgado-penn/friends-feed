<script>
  import { onMount } from "svelte"
  import { fade } from "svelte/transition"
  import JoinGame from "./feedCards/JoinGame.svelte";
  import OddsBoost from "./feedCards/OddsBoost.svelte";
  import PlaceBet from "./feedCards/PlaceBet.svelte";
  import PlayGame from "./feedCards/PlayGame.svelte";
  import PromotionCard from "./feedCards/PromotionCard.svelte";
  import TweetCard from "./feedCards/TweetCard.svelte";
  import WinBet from "./feedCards/WinBet.svelte";

  export let cardType = "place_bet";
  export let event;

  const feedCardClasses = ["feed-card"];
  const noMarginCards = ["win_bet", "promotion", "play_game", "join_game"]
  let mounted = false

  onMount(() => setTimeout(() => mounted = true, 200))

  $: if (noMarginCards.includes(cardType)) feedCardClasses.push("no-margin");
</script>

{#if mounted}
  <article in:fade class={feedCardClasses.join(" ")}>
    {#if cardType === "place_bet"}
      <PlaceBet {event} />
    {/if}

    {#if cardType === "win_bet"}
      <WinBet {event} />
    {/if}

    {#if cardType === "play_game"}
      <PlayGame {event} />
    {/if}

    {#if cardType === "join_game"}
      <JoinGame {event} />
    {/if}

    {#if cardType === "odds_boost"}
      <OddsBoost {event} />
    {/if}

    {#if cardType === "promotion"}
      <PromotionCard {event} />
    {/if}

    {#if cardType === "tweet"}
      <TweetCard {event} />
    {/if}
  </article>
  {/if}

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
    width: 100%;
  }
</style>
