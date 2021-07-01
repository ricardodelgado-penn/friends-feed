<script>
import IconAndTitle from './components/IconAndTitle.svelte';
import ThumbsUpFooter from './components/ThumbsUpFooter.svelte';
import TimeAgoStamp from './components/TimeAgoStamp.svelte';

export let event
</script>

<div class="upper-win-card">
  <TimeAgoStamp />

  <IconAndTitle>
    <span slot="icon">Icon</span>

    <span slot="title">{event.username} {event.title}</span>
  </IconAndTitle>

  <div class="row wagered font-caption">
    <span class="font-upper">Wagered</span>

    <span>{event.data[3]}</span>
  </div>

  <div class="row">
    <span class="font-upper font-subtitle-1 font-bold">Won</span>

    <span class="font-subtitle-2">{event.data[2]}</span>
  </div>
</div>

<div class="lower-win-bet font-caption">
  <div>
    {event.data[2]}
  </div>
  
  <div class="win-bet-detail">
    {event.data[1]}
  </div>

  <div class="row odds-row">
    <span class="font-bold font-upper">Josh Anderson-Yes</span>

    <span class="odds">+698</span>
  </div>

  <ThumbsUpFooter>
    <span slot="count">34</span>
  </ThumbsUpFooter>
</div>

<style>

.lower-win-bet {
  line-height: 1.65;
  padding: 16px;
}

.wagered {
  line-height: 1.5;
}
.upper-win-card {
  background: #b6dfb0;
  color: #2E762F;
  padding: 16px;
}
.row {
  display: flex;
  justify-content: space-between;
}

.odds-row {
  margin-bottom: 0.875rem;
}

.odds {
  color: #1555D0;
}
</style>
