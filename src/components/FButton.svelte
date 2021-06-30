<script>
  export let click
</script>

<button class="button" on:click={click}>
  <slot></slot>
</button>

<style>
.button {
  background: white;
  border: 1px solid rgba(0, 0, 0, 0.07);
  border-radius: 2px;
  box-shadow: 1px 1px 1px rgba(0, 0, 0, 0.2);
  color: #1555d0;
  overflow: hidden;
  height: 48px;
  width: 48px;
}
</style>