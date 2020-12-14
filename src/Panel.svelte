<script>
  export let hdrbg = 'darkslategrey'
  export let hdrclr = 'whitesmoke'
  export let showcontent = true
  $: cssVarStyles = `
			--hdrbg:${hdrbg};
			--hdrclr:${hdrclr};
		`
</script>

<style>
  .panel {
    box-sizing: border-box;
    box-shadow: 0 2px 4px #999999;
    height: auto;
    width: auto;
    margin-bottom: 10px;
  }
  .hdr {
    background-color: var(--hdrbg);
    color: var(--hdrclr);
    padding: 4px 10px;
    border-radius: 4px 4px 0 0;
    font-size: 20px;
    height: auto;
    cursor: pointer;
  }
  .content {
    padding: 10px;
    height: auto;
    font-size: 14px;
    display: none;
    transition: all 1s;
  }
  .content.active {
    display: block;
  }
</style>

<main class="panel" style={cssVarStyles}>
  <div class="hdr" on:click>
    <slot name="header">
      <div class="sectiontitle">
        <slot name="header" />
      </div>
      <div class="subtitle">
        <slot name="subtitle" />
      </div>
    </slot>
  </div>
  <div class="content" class:active={showcontent}>
    <slot name="content" />
  </div>
</main>
