<script>
  import Topnav from "./Topnav.svelte";
  import Profile from "./Profile.svelte";
  import Skills from "./Skills.svelte";
  import WorkHistory from "./WorkHistory.svelte";

  let components = [
    {name: 'Profile', comp: Profile},
    {name: 'Technical Skills', comp: Skills},
    {name: 'Work History', comp: WorkHistory}
  ]
  let currComp = components[0]; 
</script>

<div id="app">
  <div class="container">
    <Topnav />

    <div class="content">
      <nav>
        {#each components as comp}
          <button class="nav-btn" on:click={() => {currComp = comp}} 
            class:hilite={currComp === comp}>{comp.name}</button>
        {/each}
      </nav>
      <div class="content-body">
        <div class="section-title">{currComp.name}</div>
        <svelte:component this={currComp.comp} />
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

  .content {
    box-sizing: border-box;
    height: 80vh;
    overflow: hidden;
    display: flex;
    flex-flow: column;
    background: linear-gradient(aliceblue,lightblue,aliceblue);
  }
  .content-body {
    box-sizing: border-box;
    height: 70vmax;
    font-size: 3vmin;
    width: inherit;
    margin: 1vh 1vw;
    padding: 1vh 1vw;
    overflow: hidden;
  }
  nav {
    display: grid;
    grid-template-columns: auto auto auto;
    margin: 1vw;
    gap: 1vw;
  }
  .nav-btn {
    border-radius: 10px 10px 0 0;
    border: none;
    padding: 1vh 1vw;
    width: inherit;
    font-size: 3vmin;
    font-family: Orbitron;
    cursor: pointer;
  }
  .nav-btn.hilite {
    background-color: lightcyan;
  }
  .section-title {
    background: linear-gradient(lightgrey, darkgrey) no-repeat;
    padding: 2vmin 4vmin;
    margin: 0 0 1vmax;
    font-size: 3vmin;
  }
</style>
