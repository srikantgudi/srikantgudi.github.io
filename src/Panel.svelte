<script>
  export let hdrbg = 'darkslategrey'
  export let hdrclr = 'whitesmoke'
  export let hdrfontsize = '16px'
  export let showcontent = true
  export let contentheight = 'auto'
  $: cssVarStyles = `
			--hdrbg:${hdrbg};
			--hdrclr:${hdrclr};
      --hdrfont:${hdrfontsize};
      --contentheight:${contentheight}
		`
</script>

<style>
  .panel {
    box-sizing: border-box;
    box-shadow: 0 2px 4px #999999;
    height: auto;
    width: auto;
    border-radius: 10px 10px 0 0;
    margin-bottom: 10px;
  }
  .hdr {
    background-color: var(--hdrbg);
    color: var(--hdrclr);
    padding: 4px 10px;
    border-radius: 10px 10px 0 0;
    font-size: var(--hdrfont);
    height: auto;
    cursor: pointer;
  }
  .content {
    font-family: Montserrat;
    padding: 10px;
    overflow-y: auto;
    max-height: var(--contentheight);
    font-size: 16px;
    display: none;
    transition: all 1s;
  }
  .content.active {
    display: block;
  }
  .title {
    font-family: Orbitron;
  }
  .subtitle {
    font-size: 12px;
  }
  @media screen and (max-width: 719px) {
    .hdr,
    .content {
      font-size: 12px;
      height: 50%;
    }
  }
</style>

<main class="panel" style={cssVarStyles}>
  <div class="hdr" on:click>
    <div class="title">
      <slot name="title" />
    </div>
    <div class="subtitle">
      <slot name="subtitle" />
    </div>
  </div>
  <div class="content" class:active={showcontent}>
    <slot name="content" />
  </div>
</main>
