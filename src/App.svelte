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
  
  const goTab = (delta) => {
    tabIdx += delta;
    if (tabIdx < 0) {tabIdx = 0}
    if (tabIdx > ntabs-1) {tabIdx = ntabs-1}
    prevTab = (tabIdx === 0 ? '' : tabs[tabIdx-1])
    nextTab = (tabIdx === ntabs - 1 ? '' : tabs[tabIdx+1])
  }
</script>

<div id="app">
  <Topnav />

  <div class="container">
    <button disabled={tabIdx === 0} class="navbtn" on:click={() => goTab(-1)>{prevTab}</button>
    <div class="content">
      <div class="sectiontitle center">{curTab.tab}</div>
      <div class="content-body">
        <svelte:component this={tabs[tabIdx].comp} />
      </div>
    </div>
    <button class="navbtn next" on:click={() => goTab(1)}>{nextTab}</button>
    </div>
</div>

<style>
  :root {
    background: linear-gradient(aliceblue, lightblue, aliceblue) no-repeat;
    height: 99%;
    overflow: hidden;
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
    width: 80vw;
    height: 70;
    overflow: hidden;
    margin: 0 auto;
    display: flex;
    flex-flow: column;
    gap: 4px;
    padding: 10px;
    background: linear-gradient(aliceblue,lightblue,aliceblue);
    border-radius: 10px 10px 8px 8px;
  }
  .content-body {
    box-sizing: border-box;
    height: 60vh;
    margin: 10px;
    overflow-y: auto;
  }
  .center {
    text-align: center;
    justify-content: center;
  }
  .navbtn {
    border-radius: 40% 40% 0 0;
    height: 2em;
    width: 100%;
    cursor: pointer;
    margin: 0 auto;
    position: relative;
    border: none;
    font-size: 24px;
    background: linear-gradient(#999999, #cccccc);
    color: #666666;
  }
  .navbtn.next {
    border-radius: 0 0 40% 40%;
    background: linear-gradient(#cccccc,#999999);
  }
  @media screen and (max-width: 719px) {
    .tab {
      width: 100%;
      margin: 0 0 10px;
      height: auto;
    }
    .tab-content {
      height: auto;
      padding-bottom: 10px;
    }
  }
</style>
