<script>
export let click
export let odds = false
export let block = false
export let outline = false

const buttonClasses = new Array('button')

$: if (odds) buttonClasses.push('odds')
$: if (block) buttonClasses.push('block')
$: if (outline) buttonClasses.push('outline')
</script>

<button class={buttonClasses.join(' ')} on:click={click}>
  <slot></slot>
</button>

<style>
.button {
  --fbutton-bg: #1555d0;
  --fbutton-border: 1px solid #1555d0;
  --fbutton-font-color: white;
}

.outline {
  --fbutton-bg: white;
  --fbutton-font-color: #1555d0;
}

.odds {
  --fbutton-bg: white;
  --fbutton-font-color: #1555d0;
}
.button {
  background: var(--fbutton-bg);
  border: var(--fbutton-border);
  border-radius: 2px;
  color: var(--fbutton-font-color);
  overflow: hidden;
}

.button.block {
  width: 100%;
}

.button.odds {
  background: white;
  border: 1px solid rgba(0, 0, 0, 0.07);
  box-shadow: 1px 1px 1px rgba(0, 0, 0, 0.2);
  height: 48px;
  width: 48px;
}
</style>