<script>
  import { beforeUpdate, onMount } from 'svelte'
  export let timestamp

  let timestampDifference

  const calculateTimestampDiff = () => {
    const now = ~~(+new Date() / 1000);
  
    timestampDifference = millisToMinutesAndSeconds(now - (new Date(timestamp).getTime() / 1000))
  }

  const millisToMinutesAndSeconds = (millis) => Math.abs(Math.floor(millis / 60000));

  beforeUpdate(() => {
    calculateTimestampDiff()
  })

  onMount(() => {
    calculateTimestampDiff()
  })
</script>

<header class="t-ago-header font-body-2">{timestampDifference} Mins Ago</header>

<style>
.t-ago-header {
  margin-bottom: 0.875rem;
}
</style>
