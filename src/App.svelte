<script>
  import Topnav from "./Topnav.svelte";
  import Profile from "./Profile.svelte";
  import Skills from "./Skills.svelte";
  import WorkHistory from "./WorkHistory.svelte";
  import Academic from "./Academic.svelte";

  let contentId = 1;
  let zoomTab = false;
  let tabs = [
    {tab: 'Profile', comp: Profile},
    {tab: 'Technical Skills', comp: Skills},
    {tab: 'Work Experience', comp: WorkHistory},
    {tab: 'Acacemic', comp: Academic}
  ];
  let curTab;
  let tabIdx = 0;
  let prevTab;
  let nextTab;

  $: curTab = tabs[tabIdx];
  $: ntabs = tabs.length;
  $: nextTab = (tabIdx === ntabs - 1 ? '' : tabs[tabIdx+1].tab)
  $: prevTab = (tabIdx === 0 ? '' : tabs[tabIdx-1].tab)
  
  const goTab = (delta) => {
    tabIdx += delta;
    if (tabIdx < 0) {tabIdx = 0}
    if (tabIdx > ntabs-1) {tabIdx = ntabs-1}
  }
</script>

<div id="app">
  <div class="container">
    <Topnav />
    <div class="content">
      <div class="content-body">
        <Profile />
        <Skills />
        <WorkHistory />
        <Academic />
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
    margin: 10px;
    overflow-y: auto;
  }
  @media screen and (max-width: 719px) {
    .content {
      width: 100%;
      margin: 0 0 10px;
      height: auto;
    }
  }
</style>
