<script>
  import FilledThumbsUpIcon from '../../../assets/icons/filled-thumbs-up.svelte'
</script>

<div class="thumbs-up">
  <FilledThumbsUpIcon class="thumbs-up-icon" />

  <slot name="count"></slot>
</div>

<style>
  .thumbs-up {
    cursor: pointer;
    display: flex;
    gap: 8px;
  }
</style>
