<script>
  import IconAndTitle from "./components/IconAndTitle.svelte";
  import ThumbsUpFooter from "./components/ThumbsUpFooter.svelte";
  import TimeAgoStamp from "./components/TimeAgoStamp.svelte";

  export let event;
</script>

<section class="join-game">
  <div class="header-info">
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
  </div>

  <div class="header-image">
    <figure>
      <img
        src="https://penn-interactive-sb-us-east-1-dev.imgix.net/casino.game/17a578c8-77ac-4cd9-99a6-02b35b44d50f/default-94a5005b5938815461ea04dbe772bbce.jpg?w=300"
        alt="Game Banner"
      />
    </figure>
  </div>

  <div class="join-game-details">
    <div class="join-link">
      <a href={event.deeplink_url} target="_parent">Join Now</a>
    </div>
  
    <ThumbsUpFooter count={event.likes} />
  </div>
</section>

<style>
  .header-info {
    padding: 16px 16px 0;
  }
  .join-game-details {
    padding: 0 16px 16px;
  }
  .join-game .join-link {
    margin-bottom: 0.875rem;
  }
  figure {
    display: block;
    margin-block-start: 0;
    margin-block-end: 0;
    margin-inline-start: 0;
    margin-inline-end: 0;
    padding: 0;
    margin: 10px auto;
    max-width: 410px;
    width: 100%;
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
