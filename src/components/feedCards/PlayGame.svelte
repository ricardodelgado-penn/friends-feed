<script>
  import IconAndTitle from "./components/IconAndTitle.svelte";
  import ThumbsUpFooter from "./components/ThumbsUpFooter.svelte";
  import TimeAgoStamp from "./components/TimeAgoStamp.svelte";

  export let event;
</script>

<TimeAgoStamp />

<IconAndTitle>
  <icon>Icon</icon>

  <span slot="title">{event.username} {event.title}</span>
  <div style="background-image: {event.thumbnail_url}" />
</IconAndTitle>

<div class="content font-caption" />

<div class="play-link">
  <a href={event.deeplink_url} target="_parent">Play Now</a>
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
