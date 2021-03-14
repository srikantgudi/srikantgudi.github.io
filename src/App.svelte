<script>
  import Topnav from "./Topnav.svelte";
  import Profile from "./Profile.svelte";
  import Skills from "./Skills.svelte";
  import WorkHistory from "./WorkHistory.svelte";

  let components = [
    {name: 'Personal Info', comp: Topnav},
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
  <div class="container">
    <div class="nav-buttons-bar">
    </div>
    <div class="content-title">
      <button class="nav-btn" on:click={() => goComp(-1)}>&lt;</button>
      <div>{components[curIdx].name}</div>
      <button class="nav-btn next" on:click={() => goComp(1)}>&gt;</button>
    </div>
    <div class="content">
      <svelte:component this={currComp} />
    </div>
  </div>
</div>
