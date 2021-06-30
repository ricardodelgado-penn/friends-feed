<script>
import { onMount } from 'svelte'
import {Socket} from 'phoenix-socket'

import FeedCard from './components/FeedCard.svelte'

onMount(() => {
	const socket = new Socket(
    'ws://feed.penngineering.io:4000/socket', {
    vsn: '2.0.0'
  })

  socket.connect()

  console.log({ socket })
  let channel = socket.channel("feed:all", {})
  channel.join()
    .receive("ok", resp => {
      console.log("Joined successfully", resp)
      resp.events.forEach(element => {
        console.log({ event })
      });
    })
    .receive("error", resp => { console.log("Unable to join", resp) })

  channel.on("new_event", resp => {
    console.log("New Event", resp)
    console.log(resp.event)
  })	
})
</script>

<main>
  <FeedCard cardType="join_game"/>

  <FeedCard cardType="odds_boost"/>

  <FeedCard cardType="place_bet"/>

  <FeedCard cardType="play_game"/>

  <FeedCard cardType="promotion"/>

  <FeedCard cardType="tweet"/>

  <FeedCard cardType="win_bet"/>
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
	}
</style>