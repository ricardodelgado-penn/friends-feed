<script>
  import IconAndTitle from "./components/IconAndTitle.svelte";
  import ThumbsUpFooter from "./components/ThumbsUpFooter.svelte";
  import TimeAgoStamp from "./components/TimeAgoStamp.svelte";

  export let event;
</script>

<TimeAgoStamp />
<IconAndTitle>
  <span slot="icon"
    ><img class="avatar" src="/img/{event.username}.png" alt="Profile" /></span
  >

  <span slot="title">{event.username} {event.title}</span>
</IconAndTitle>
<div class="header-image">
  <figure>
    <img
      src="https://penn-interactive-sb-us-east-1-dev.imgix.net/casino.game/f748048b-99bf-4a89-9d44-d27dda2cc264/default-40377aa39ed0f9c405f3843512e42787.jpg?w=300"
      alt="Game Banner"
    />
  </figure>
</div>

<div class="join-link">
  <a href={event.deeplink_url} target="_parent">Play Now</a>
</div>

<ThumbsUpFooter>
  <span slot="count">{event.likes}</span>
</ThumbsUpFooter>

<style>
  .join-link {
    margin-bottom: 0.875rem;
  }
  figure {
    padding: 0;
    margin: -14px;
    margin-bottom: 10px;
    margin-top: 10px;
    width: 410px;
  }
  figure img {
    width: 100%;
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
