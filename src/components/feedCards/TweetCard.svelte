<script>
  import IconAndTitle from "./components/IconAndTitle.svelte";

  import TimeAgoStamp from "./components/TimeAgoStamp.svelte";

  export let event;
  console.log({ event });
</script>

<TimeAgoStamp />

<IconAndTitle>
  <span slot="icon"
    ><img class="avatar" src="/img/{event.username}.png" alt="Profile" /></span
  >

  <span slot="title">{event.username} {event.title}</span>
</IconAndTitle>

<div class="tweet-body font-body-2">
  {event.body}
</div>

<div class="tweet-link">
  <a href={event.deeplink_url} target="_blank">View on Twitter</a>
</div>

<style>
  .tweet-body {
    margin-bottom: 0.875rem;
  }
  .avatar {
    width: 30px;
    height: 30px;
    border-radius: 30px;
    vertical-align: middle;
    margin-right: 4px;
    border: solid 1px grey;
  }
</style>
