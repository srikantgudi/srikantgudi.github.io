<script>
  import Topnav from "./Topnav.svelte";
  import Profile from "./Profile.svelte";
  import Skills from "./Skills.svelte";
  import WorkHistory from "./WorkHistory.svelte";
  import Academic from "./Academic.svelte";

  let contentId = 1;
  let zoomTab = false;
  let curTab = 0;
</script>

<div id="app">
  <Topnav />

  <div class="content">
    <!-- <div class="tabs">
      <div class="tab" class:active={curTab === 1}>
        <div class="title-nav">
          <div
            class="tab-title"
            class:current={curTab === 1}
            on:click={() => {
              curTab = 1;
            }}
          >
            Profile
          </div>
          <button
            class="close-btn"
            class:active={curTab === 1}
            on:click={() => {
              curTab = 0;
            }}>&times;</button
          >
        </div>
        <div class="tab-content" class:active={curTab === 1}>
          <Profile />
        </div>
      </div>
      <div class="tab" class:active={curTab === 2}>
        <div class="title-nav">
          <div
            class="tab-title"
            class:current={curTab === 2}
            on:click={() => {
              curTab = 2;
            }}
          >
            Technical Skills
          </div>
          <button
            class="close-btn"
            class:active={curTab === 2}
            on:click={() => {
              curTab = 0;
            }}>&times;</button
          >
        </div>
        <div class="tab-content" class:active={curTab === 2}>
          <Skills />
        </div>
      </div>
      <div class="tab" class:active={curTab === 3}>
        <div class="title-nav">
          <div
            class="tab-title"
            class:current={curTab === 3}
            on:click={() => {
              curTab = 3;
            }}
          >
            Work History
          </div>
          <button
            class="close-btn"
            class:active={curTab === 3}
            on:click={() => {
              curTab = 0;
            }}>&times;</button
          >
        </div>
        <div class="tab-content" class:active={curTab === 3}>
          <WorkHistory />
        </div>
      </div>
    </div> -->
    <div class="tabs">
      <div class="tab">
        <div class="tab-title">Profile</div>
        <div class="tab-content">
          <Profile />
        </div>
      </div>
      <div class="tab">
        <div class="tab-title">Skills</div>
        <div class="tab-content">
          <Skills />
        </div>
      </div>
      <div class="tab">
        <div class="tab-title">Work History</div>
        <div class="tab-content">
          <WorkHistory />
        </div>
      </div>
    </div>
  </div>
</div>

<style>
  :root {
    background: linear-gradient(aliceblue, lightblue, aliceblue) no-repeat;
    height: 100%;
  }
  #app {
    font-family: Roboto;
    box-shadow: 0 0 4px #999;
    margin: 0 1em;
    background: linear-gradient(lightblue, navy);
    min-height: 94vh;
    padding-bottom: 20px;
  }

  .content {
    display: flex;
    align-items: center;
    margin: 10px 15px;
    gap: 10px;
  }
  .tabs {
    display: flex;
    flex-flow: row wrap;
    gap: 1vw 1vh;
    margin: 0 auto;
  }
  .tab {
    flex: 1;
    width: 30vw;
    box-shadow: 0 0 4px #eeeeee;
    height: 75vh;
    transition: all 0.5s;
  }
  .tab:hover {
    flex: 3;
  }
  .tab:hover > .tab-title {
    color: white;
    background: linear-gradient(lightblue, navy) no-repeat;
    border-radius: 10px 10px 0 0;
  }
  .tab-title {
    font-size: 18px;
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow: 0 2px 4px lightcyan;
    background: linear-gradient(blue, lightblue, blue) no-repeat;
    cursor: pointer;
    border-radius: 0 0 10px 10px;
    padding: 10px;
  }
  .tab-content {
    height: 64vh;
    overflow: hidden;
    padding: 10px 20px;
    background-color: #cccccc;
  }
  .tab:hover > .tab-content {
    overflow-y: auto;
    background-color: aliceblue;
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
