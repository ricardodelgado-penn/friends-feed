<script>
import FButton from "../FButton.svelte";

const goTo = url => {
  console.log({ url })
  window.location.href = url
}

export let event
</script>

<figure>Figure</figure>

<p class="font-body-2">
  {event.username} {event.title}

  ** Mock **
  Players who opt-in, for every $50 wager on Blackjack, will receive $5 casino bonus cash, up to $50.
</p>

<div class="end-date font-caption font-upper">
  ends 06/21/21
</div>

<div class="action-row">
  <FButton
    block
    outline
    click={() => goTo(event.deeplink_url)}>
    More Info
  </FButton>
  
  <FButton block>
    Opt In (missing)
  </FButton>
</div>

<style>
.action-row {
  display: flex;
  gap: 8px;
}

.end-date {
  color: #828181;
  margin-bottom: 0.875rem;
}
</style>
