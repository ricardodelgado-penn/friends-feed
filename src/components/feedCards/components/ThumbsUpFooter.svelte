<script>
import FilledThumbsUpIcon from '../../../assets/icons/filled-thumbs-up.svelte'

export let click
</script>

<div class="thumbs-up" on:click={click}>
  <FilledThumbsUpIcon />

  <slot name="count"></slot>
</div>

<style>
.thumbs-up {
  display: flex;
  gap: 8px;
}
</style>
