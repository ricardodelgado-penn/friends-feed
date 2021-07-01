<script>
import FButton from '../FButton.svelte';
import IconAndTitle from './components/IconAndTitle.svelte';
import ThumbsUpFooter from './components/ThumbsUpFooter.svelte';
import TimeAgoStamp from './components/TimeAgoStamp.svelte';

export let event
</script>

<section class="place-bet">
  <TimeAgoStamp />

  <IconAndTitle>
    <span slot="icon">Icon</span>

    <span slot="title">{event.username} {event.title}</span>
  </IconAndTitle>

  <div class="details">
    <div class="left">
      <div class="font-caption">{event.data[0]}</div>
      <div class="font-caption font-bold">{event.data[1].split(', ')[0]}</div>
      <div class="font-caption">{event.data[1].split(', ')[1]}</div>
    </div>

    <div class="action">
      <FButton odds>
        {event.data[2]}
      </FButton>
    </div>
  </div>

  <footer class="footer">
    <ThumbsUpFooter>
      <span slot="count">{event.likes}</span>
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