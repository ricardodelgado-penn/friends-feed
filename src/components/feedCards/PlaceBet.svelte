<script>
import FButton from "../FButton.svelte";

const getWs = () => {
  const ws = new WebSocket('ws://19f6e02fac60.ngrok.io/socket/websocket?token=undefined&vsn=2.0.0')
  
  ws.onmessage = resp => console.log({ messageResp: resp })

  ws.onopen = resp => console.log({ openResp: resp })
}
</script>

<section>
  <header class="place-bet-header font-body-2">14 Mins Ago</header>

  <div class="title-row">
    <span>Icon</span>

    <span>User1234 Has Placed a Bet</span>
  </div>

  <div>
    <div>PHI 76ers @ BKN Nets</div>
    <div>POINT SPREAD, PHI 76ers -1.5</div>
  </div>

  <div class="action">
    <FButton click={getWs}>
      <span>Label</span>

      <span>Odds</span>
    </FButton>
  </div>

  <footer>
    "Thumbs Up" 123
  </footer>
</section>

<style>
.place-bet-header {
  margin-bottom: 2rem;
}
</style>