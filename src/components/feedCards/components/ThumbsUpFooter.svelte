<script>
  import FilledThumbsUpIcon from '../../../assets/icons/filled-thumbs-up.svelte'

  export let count
</script>

<div class="thumbs-up">
  <FilledThumbsUpIcon
    increaseCount={() => count = count + 1}
    decreaseCount={() => count = count - 1}
    class="thumbs-up-icon" />

  {count}
</div>

<style>
  .thumbs-up {
    cursor: pointer;
    display: flex;
    gap: 8px;
  }
</style>
