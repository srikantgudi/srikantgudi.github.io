<script>
  import Topnav from "./Topnav.svelte";
  import Profile from "./Profile.svelte";
  import Skills from "./Skills.svelte";
  import WorkHistory from "./WorkHistory.svelte";

  let components = [
    {key: 'profile', name: 'Profile', comp: Profile},
    {key: 'skills', name: 'Technical Skills', comp: Skills},
    {key: 'exp', name: 'Work History', comp: WorkHistory}
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
  <Topnav />
  <div class="menubar">
    {#each components as component}
    <button class="menuitem" class:active={currComp === component.comp} on:click={() => {currComp = component.comp}}>
      {component.name}
    </button>
    {/each}
  </div>
  <div class="content">
    <svelte:component this={currComp} />
  </div>
</div>
