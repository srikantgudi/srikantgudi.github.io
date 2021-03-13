<script>
  import Topnav from "./Topnav.svelte";
  import Profile from "./Profile.svelte";
  import Skills from "./Skills.svelte";
  import WorkHistory from "./WorkHistory.svelte";
</script>

<div id="app">
  <div class="container">
    <Topnav />
    <div class="content">
      <div class="content-body">
        <Profile />
        <Skills />
        <WorkHistory />
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
