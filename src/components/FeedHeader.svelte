<article class="userinfo">
  <div class="userinfo-inner">
    <div class="left">Avatar</div>

    <div class="right">
      <div class="username font-button">DPORTNOY21</div>
      <div class="location font-caption">Philadelphia, PA</div>
      <div class="standings font-caption">20 wins | 10 losses | 1 active bet</div>

      <div class="friends font-caption">
        <span>*icons*</span>

        <span>20 friends</span>
      </div>
    </div>
  </div>

  <div class="tabs">
    <slot name="tabs"></slot>
  </div>
</article>

<style>
.userinfo {
  background: linear-gradient(104deg, #102442 -22%, #010509 117%);
  box-sizing: border-box;
  color: white;
  padding: 16px 0 0;
}

.userinfo-inner {
  display: grid;
  gap: 16px;
  grid-template-columns: 64px auto;
  grid-template-rows: repeat(2, auto);
  line-height: 2;
  padding: 0 16px 0;
}

.friends {
  display: flex;
  gap: 16px;
}

.userinfo > * {
  box-sizing: border-box;
}

.tabs {
  grid-area: 2 / 1 / 3 / 3;
}
</style>
