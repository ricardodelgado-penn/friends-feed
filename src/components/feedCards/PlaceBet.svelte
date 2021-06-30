<script>
import FButton from '../FButton.svelte';
import FilledThumbsUpIcon from '../../assets/icons/thumbs-up.svelte'
</script>

<section class="place-bet">
  <header class="header font-body-2">14 Mins Ago</header>

  <div class="title-row">
    <span>Icon</span>

    <span>User1234 Has Placed a Bet</span>
  </div>

  <div class="details font-body-2">
    <div class="left">
      <div>PHI 76ers @ BKN Nets</div>
      <div>POINT SPREAD, PHI 76ers -1.5</div>
    </div>

    <div class="action">
      <FButton click={}>
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
.place-bet .title-row {
  margin-bottom: 0.875rem;
}

.place-bet .details {
  display: grid;
  grid-template-columns: auto auto;
  gap: 15px;
}
</style>