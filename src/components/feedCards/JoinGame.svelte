<script>
import IconAndTitle from "./components/IconAndTitle.svelte";
import ThumbsUpFooter from "./components/ThumbsUpFooter.svelte";

export let event
</script>

<section class="join-game">
  <div class="header-image">
    <figure>Figure</figure>
  </div>

  <IconAndTitle>
    <span slot="icon">Icon</span>

    <span slot="title">{event.username} {event.title}</span>
  </IconAndTitle>

  <div class="join-link">
    <a href="{event.deeplink_url}">Join Now</a>
  </div>

  <ThumbsUpFooter>
    <span slot="count">
      {event.likes}
    </span>
  </ThumbsUpFooter>
</section>

<style>
.join-game .join-link {
  margin-bottom: 0.875rem;
}
</style>
