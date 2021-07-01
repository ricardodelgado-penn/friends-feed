<script>
import IconAndTitle from "./components/IconAndTitle.svelte";
import ThumbsUpFooter from "./components/ThumbsUpFooter.svelte";
import TimeAgoStamp from "./components/TimeAgoStamp.svelte";

export let event
</script>

<TimeAgoStamp />

<IconAndTitle>
  <icon>Icon</icon>

  <span slot="title">{event.username} {event.title}</span>
</IconAndTitle>

<div class="content font-caption">
  <span class="font-bold">
    Blackjack, (missing)
  </span>

  Top Rated (missing)
</div>

<div class="play-link">
  <a href="{event.deeplink_url}">Play Now</a>
</div>

<ThumbsUpFooter>
  <span slot="count">{event.likes}</span>
</ThumbsUpFooter>

<style>
.content,
.play-link {
  margin-bottom: 0.875rem;
}
</style>
