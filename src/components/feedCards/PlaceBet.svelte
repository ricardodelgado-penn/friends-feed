<script>
  import FButton from "../FButton.svelte";
  import IconAndTitle from "./components/IconAndTitle.svelte";
  import ThumbsUpFooter from "./components/ThumbsUpFooter.svelte";
  import TimeAgoStamp from "./components/TimeAgoStamp.svelte";

  export let event;
</script>

<section class="place-bet">
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

  <div class="details">
    <div class="left">
      <div class="font-caption">{event.data[0]}</div>
      <div class="font-caption font-bold">{event.data[1]}</div>
      <div class="font-caption">{event.data[2]}</div>
    </div>

    <div class="action">
      <FButton odds>
        {event.data[3]}
      </FButton>
    </div>
  </div>

  <footer class="footer">
    <ThumbsUpFooter count={event.likes} />
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
  .avatar {
    width: 30px;
    height: 30px;
    border-radius: 30px;
    vertical-align: middle;
    margin-right: 4px;
    border: solid 1px grey;
  }
</style>
