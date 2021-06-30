<script>
import IconAndTitle from "./components/IconAndTitle.svelte";

import TimeAgoStamp from "./components/TimeAgoStamp.svelte";

</script>
<TimeAgoStamp />

<IconAndTitle>
  <span slot="icon">Icon</span>

  <span slot="title">Barstool Sportsbook</span>
</IconAndTitle>

<div class="tweet-body font-body-2">
  Ben Simmons has not missed a three pointer all season, you can get him +800 tonight on the Barstool Sportsbook @betthehoops
</div>

<div class="tweet-link">
  <a href="test">View on Twitter</a>
</div>

<style>
.tweet-body {
  margin-bottom: 0.875rem;
}
</style>
