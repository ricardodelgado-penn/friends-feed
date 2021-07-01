<script>
  import FilledThumbsUpIcon from '../../../assets/icons/filled-thumbs-up.svelte'

  export let selected = false

  const click = () => {
    selected = !selected
  }
</script>

<div class="thumbs-up" on:click={click}>
  <div class={selected ? 'selected' : ''}>
    <FilledThumbsUpIcon class="thumbs-up-icon" />
  </div>

  <slot name="count"></slot>
</div>

<style>
  .thumbs-up {
    --tu-icon-color: #d6d6d6;
  }
  .selected {
    --tu-icon-color: #C58E01;
  }
  .thumbs-up {
    color: var(--tu-icon-color);
    cursor: pointer;
    display: flex;
    gap: 8px;
  }

  .selected {
    animation: bump 300ms;
  }

  @keyframes bump {
    from {
      transition: scale(1);
    }

    50% {
      transition: scale(1.3);
    }

    to {
      transition: scale(1);
    }
  }
</style>
