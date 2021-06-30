<script>
import IconAndTitle from "./components/IconAndTitle.svelte";
import ThumbsUpFooter from "./components/ThumbsUpFooter.svelte";
import TimeAgoStamp from "./components/TimeAgoStamp.svelte";

</script>

<TimeAgoStamp />

<IconAndTitle>
  <icon>Icon</icon>

  <span slot="title">AlSmith achieved a high score</span>
</IconAndTitle>

<div class="content font-caption">
  <span class="font-bold">
    Blackjack,
  </span>

  Top Rated
</div>

<div class="play-link">
  <a href="test">Play Now</a>
</div>

<ThumbsUpFooter>
  <span slot="count">24</span>
</ThumbsUpFooter>

<style>
.content,
.play-link {
  margin-bottom: 0.875rem;
}
</style>
