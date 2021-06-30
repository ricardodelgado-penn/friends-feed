<script>
import FButton from '../FButton.svelte';
import IconAndTitle from './components/IconAndTitle.svelte';
import ThumbsUpFooter from './components/ThumbsUpFooter.svelte';
import TimeAgoStamp from './components/TimeAgoStamp.svelte';
</script>

<section class="place-bet">
  <TimeAgoStamp />

  <IconAndTitle>
    <span slot="icon">Icon</span>

    <span slot="title">User1234 Has Placed a Bet</span>
  </IconAndTitle>

  <div class="details">
    <div class="left">
      <div class="font-caption">PHI 76ers @ BKN Nets</div>
      <div class="font-caption font-bold">POINT SPREAD</div>
      <div class="font-caption">PHI 76ers -1.5</div>
    </div>

    <div class="action">
      <FButton>
        Odds
      </FButton>
    </div>
  </div>

  <footer class="footer">
    <ThumbsUpFooter>
      <span slot="count">23</span>
    </ThumbsUpFooter>
  </footer>
</section>

<style>

.place-bet .details {
  margin-bottom: 0.875rem;
}

.place-bet .details {
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 15px;
}

.place-bet .details .left > * {
  line-height: 1.4;
}
</style>