<script>
import IconAndTitle from "./components/IconAndTitle.svelte";
import ThumbsUpFooter from "./components/ThumbsUpFooter.svelte";


</script>

<section class="join-game">
  <div class="header-image">
    <figure>Figure</figure>
  </div>

  <IconAndTitle>
    <span slot="icon">Icon</span>

    <span slot="title">Mike12 is playing Double Stacks</span>
  </IconAndTitle>

  <div class="join-link">
    <a href="test">Join Now</a>
  </div>

  <ThumbsUpFooter>
    <span name="count">
      26
    </span>
  </ThumbsUpFooter>
</section>
