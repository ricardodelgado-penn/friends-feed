<script>
  import CircleLightning from "../../assets/icons/circle-lightning.svelte";

  export let event;
</script>

<p class="first-line font-subtitle-1">Invite your friends for an odds boost!</p>

<p class="font-body-2">
  Send a link to your friends to join and follow you on a Bartool Sportsbook
</p>

<div class="invite-link font-bold">
  Invite Link

  <CircleLightning />
</div>

<style>
  .first-line {
    margin-top: 0;
  }

  .invite-link {
    align-items: center;
    background: url("/img/invite-bg.svg");
    background-position: center;
    background-size: cover;
    color: white;
    display: flex;
    font-size: 1rem;
    font-style: italic;
    gap: 24px;
    padding: 1.5rem;
    margin: 0 -15px;
    text-transform: uppercase;
  }
</style>
