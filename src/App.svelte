<script>
  import Topnav from "./Topnav.svelte";
  import Profile from "./Profile.svelte";
  import Skills from "./Skills.svelte";
  import WorkHistory from "./WorkHistory.svelte";

  let msg = '';
  let comps = [
    {name: 'Profile', comp: Profile},
    {name: 'Technical Skills', comp: Skills},
    {name: 'Work History', comp: WorkHistory}
  ];
  let idx = 0;
  let currComp = comps[0].comp;
  let lastIdx;
  $: lastIdx = comps.length - 1;

  
  $: {
    currComp = comps[idx].comp;
  }
  
  const goComp = (delta) => {
    idx += delta
    if (idx > lastIdx) {
      idx = 0
    } else if (idx < 0) {
      idx = lastIdx
    }
  }
  
</script>

<div id="app">
  <div class="container">
    <Topnav />

    <div class="content">
      <div class="content-body">
        <button disabled={idx === 0} class="nav-btn" on:click={() => goComp(-1)}>
          &laquo;
        </button>
        <div class="component">
          <svelte:component this={currComp} />
        </div>
        <button disabled={idx === lastIdx} class="nav-btn next" on:click={() => goComp(1)}>
          &raquo;
        </button>
      </div>
    </div>
  </div>
</div>

<style>
  :root {
    background: linear-gradient(aliceblue, lightblue, aliceblue) no-repeat;
    height: 99%;
    overflow-y: hidden;
  }
  #app {
    font-family: Roboto;
    box-shadow: 0 0 4px #999;
    margin: 0 1em;
    background: linear-gradient(lightblue, navy);
    min-height: 97vh;
    padding-bottom: 10px;
  }

  .container {
    display: grid;
    grid-template-rows: auto 1fr auto;
    align-items: center;
    gap: 10px;
    width: 80vw;
    margin: 10px auto;
  }
  .content {
    box-sizing: border-box;
    height: 80vh;
    overflow: hidden;
    margin: 0 auto;
    display: flex;
    flex-flow: column;
    gap: 4px;
    background: linear-gradient(aliceblue,lightblue,aliceblue);
    border-radius: 10px 10px 8px 8px;
  }
  .content-body {
    box-sizing: border-box;
    height: 70vh;
    width: 60vw;
    margin: 10px;
    overflow: hidden;
  }
  .component {
    height: 60vh;
    overflow: hidden;
    margin: 4px 20px;
    padding: 10px;
    box-shadow: 0 0 2px #999999;
  }
  .nav-btn {
    width: 100%;
    border-radius: 10px 10px 0 0;
    border: none;
    font-size: 18px;
  }
  .nav-btn.next {
    border-radius: 0 0 10px 10px;
  }
  @media screen and (max-width: 719px) {
    .content-body  {
      width: 100%;
      margin: 0 0 10px;
      height: auto;
    }
  }
</style>
