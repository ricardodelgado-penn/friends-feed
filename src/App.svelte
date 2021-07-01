<script>
  import { onMount } from "svelte";
  import { Socket } from "phoenix-socket";
  import { events as storeEvents } from "./store/events.js";
  import FeedCard from "./components/FeedCard.svelte";
  import FeedHeader from "./components/FeedHeader.svelte";
  import FeedTabs from "./components/FeedTabs.svelte";

  let feedItems = [];

  onMount(() => {
    const socket = new Socket("ws://feed.penngineering.io:4000/socket", {
      vsn: "2.0.0",
    });

    socket.connect();

    let channel = socket.channel("feed:all", {});
    channel
      .join()
      .receive("ok", ({ events }) => {
        feedItems = events;
        storeEvents.update((e) => feedItems);
        visible = true;
      })
      .receive("error", (resp) => {
        console.log("Unable to join", resp);
      });

    channel.on("new_event", ({ event }) => {
      feedItems = [event, ...feedItems];
      storeEvents.update((e) => feedItems);
    });
  });
</script>

<main>
  <FeedHeader>
    <FeedTabs slot="tabs" />
  </FeedHeader>

  {#each feedItems as event (`${event.id}-${Math.random() * 100}`)}
    <FeedCard cardType={event.type} {event} />
  {/each}
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    width: 100%;
  }
</style>
