<script>
import FButton from '../FButton.svelte';
import FilledThumbsUpIcon from '../../assets/icons/filled-thumbs-up.svelte'
</script>

<section class="place-bet">
  <header class="header font-body-2">14 Mins Ago</header>

  <div class="title-row">
    <span>Icon</span>

    <span>User1234 Has Placed a Bet</span>
  </div>

  <div class="details">
    <div class="left">
      <div class="font-body-2">PHI 76ers @ BKN Nets</div>
      <div class="font-button">POINT SPREAD</div>
      <div class="font-body-2">PHI 76ers -1.5</div>
    </div>

    <div class="action">
      <FButton>
        Odds
      </FButton>
    </div>
  </div>

  <footer class="footer">
    <FilledThumbsUpIcon />

    23
  </footer>
</section>

<style>

.place-bet .header,
.place-bet .title-row,
.place-bet .details {
  margin-bottom: 0.875rem;
}

.place-bet .details {
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 15px;
}
</style>