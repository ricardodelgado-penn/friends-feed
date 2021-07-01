<script>
  import FButton from "../FButton.svelte";

  const goTo = (url) => {
    window.location.href = url;
  };

  export let event;
</script>

<figure>
  <img
    src="https://penn-interactive-sb-us-east-1-dev.imgix.net/users.promo/listed-pitcher-insurance/thumbnail-32bd9906c2d108c22663379256a844af.png?w=422&h=204&fit=clip"
    alt="Promotion Banner"
  />
</figure>

<div class="promo-details">
  <p class="font-body-2">
    {event.username}
    {event.title}
  </p>
  
  <div class="end-date font-caption font-upper">ends 06/21/21</div>
  
  <div class="action-row">
    <FButton block outline click={() => goTo(event.deeplink_url)}>
      More Info
    </FButton>
  
    <FButton block>Opt In</FButton>
  </div>
</div>

<style>
  .action-row {
    display: flex;
    gap: 8px;
  }

  .end-date {
    color: #828181;
    margin-bottom: 0.875rem;
  }

  figure {
    display: block;
    margin-block-start: 0;
    margin-block-end: 0;
    margin-inline-start: 0;
    margin-inline-end: 0;
    padding: 0;
    max-width: 410px;
    width: 100%;
  }
  figure img {
    width: 100%;
  }

  .promo-details {
    padding: 0 16px;
  }
</style>
