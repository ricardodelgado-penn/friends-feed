<script>
import { onMount } from 'svelte'
import {Socket} from 'phoenix-socket'
import { events as storeEvents } from './store/events.js'
import FeedCard from './components/FeedCard.svelte'

let feedItems = []

onMount(() => {
	const socket = new Socket(
    'ws://feed.penngineering.io:4000/socket', {
    vsn: '2.0.0'
  })

  socket.connect()

  let channel = socket.channel('feed:all', {})
  channel.join()
    .receive('ok', ({ events }) => {
      feedItems = events
      storeEvents.update(e => feedItems)
    })
    .receive('error', resp => { console.log('Unable to join', resp) })

  channel.on('new_event', ({ event }) => {
    console.log('New Event', event)
    feedItems = [event, ...feedItems]
    storeEvents.update(e => feedItems)
  })
})
</script>

<main>
  {#each feedItems as event (`${event.id}-${Math.random() * 100}`) }
    <FeedCard
      cardType={event.type}
      event={event} />
  {/each}

  <!-- <FeedCard cardType="join_game"/>

  <FeedCard cardType="odds_boost"/>

  <FeedCard cardType="place_bet"/>

  <FeedCard cardType="play_game"/>

  <FeedCard cardType="promotion"/>

  <FeedCard cardType="tweet"/>

  <FeedCard cardType="win_bet"/> -->
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
	}
</style>