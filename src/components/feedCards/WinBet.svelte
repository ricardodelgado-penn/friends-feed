<script>
  import IconAndTitle from "./components/IconAndTitle.svelte";
  import ThumbsUpFooter from "./components/ThumbsUpFooter.svelte";
  import TimeAgoStamp from "./components/TimeAgoStamp.svelte";

  export let event;
</script>

<div class="upper-win-card">
  <TimeAgoStamp timestamp={event.timestamp} />

  <IconAndTitle>
    <span slot="icon"
      ><img
        class="avatar"
        src="/img/{event.username}.png"
        alt="Profile"
      /></span
    >

    <span slot="title">{event.username} {event.title}</span>
  </IconAndTitle>

  <div class="row wagered font-caption">
    <span class="font-upper">Wagered</span>

    <span>{event.data[3]}</span>
  </div>

  <div class="row">
    <span class="font-upper font-subtitle-1 font-bold">Won</span>

    <span class="font-subtitle-2">{event.data[4]}</span>
  </div>
</div>

<div class="lower-win-bet font-caption">
  <div>
    {event.data[0]}
  </div>

  <div class="win-bet-detail">
    {event.data[1]}
  </div>

  <div class="row odds-row">
    <span class="font-bold font-upper">Josh Anderson-Yes</span>

    <span class="odds">+698</span>
  </div>

  <ThumbsUpFooter count={event.likes} />
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
    color: #2e762f;
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
    color: #1555d0;
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
