<script>
  import IconAndTitle from "./components/IconAndTitle.svelte";
  import ThumbsUpFooter from "./components/ThumbsUpFooter.svelte";
  import TimeAgoStamp from "./components/TimeAgoStamp.svelte";

  export let event;
</script>

<section class="join-game">
  <TimeAgoStamp />
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
  <div class="header-image">
    <figure>
      <img
        src="https://penn-interactive-sb-us-east-1-dev.imgix.net/casino.game/17a578c8-77ac-4cd9-99a6-02b35b44d50f/default-94a5005b5938815461ea04dbe772bbce.jpg?w=300"
        alt="Game Banner"
      />
    </figure>
  </div>

  <div class="join-link">
    <a href={event.deeplink_url} target="_parent">Join Now</a>
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
