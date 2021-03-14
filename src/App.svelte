<script>
  import Topnav from "./Topnav.svelte";
  import Profile from "./Profile.svelte";
  import Skills from "./Skills.svelte";
  import WorkHistory from "./WorkHistory.svelte";

  let components = [
    {name: 'Info', comp: Topnav},
    {name: 'Profile', comp: Profile},
    {name: 'Technical Skills', comp: Skills},
    {name: 'Work History', comp: WorkHistory}
  ]
  let currComp = components[0].comp;
  let curIdx = 0;

  const goComp = (delta) => {
    curIdx += delta;
    if (curIdx < 0) {
      curIdx = components.length - 1;
    } else if (curIdx > (components.length -1)) {
      curIdx = 0;
    }
    currComp = components[curIdx].comp;
  }
</script>

<div id="app">
  <div class="buttons-bar">
    <button class="nav-btn" on:click={() => goComp(-1)}>&lt;</button>
    <button class="nav-btn next" on:click={() => goComp(1)}>&gt;</button>
  </div>
  <div class="content-title">{components[curIdx].name}</div>
  <div class="content">
    <svelte:component this={currComp} />
  </div>
</div>

<style>
  #app {
    width: 80vw;
    height: 90vh;
    margin: 4vh auto;
    padding-top: 2vmin;
    box-shadow: 0 0 4px mavy;
    background: linear-gradient(lightblue,lightcyan,lightblue);
  }
  .buttons-bar {
    display: flex;
  }
  .nav-btn {
    flex: 1;
    height: 6vmax;
  }
  .content {
    height: 75vmax;
    overflow-y: auto;
    font-family: Momtserrat;
  }
  .content-title {
    font-size: 4vmax;
    font-family: Orbitron;
    display: flex;
    justify-content: center;
    margin: 1vmin;
  }
</style>
