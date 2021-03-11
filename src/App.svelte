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
    <div class="tabs">
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
      <div class="tab" class:active={curTab === 4}>
        <div class="title-nav">
          <div
            class="tab-title"
            class:current={curTab === 4}
            on:click={() => {
              curTab = 4;
            }}
          >
            Academic
          </div>
          <button
            class="close-btn"
            class:active={curTab === 4}
            on:click={() => {
              curTab = 0;
            }}>&times;</button
          >
        </div>
        <div class="tab-content" class:active={curTab === 4}>
          <Academic />
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
    height: 96vh;
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
    min-width: 20vw;
  }
  .tab.active {
    position: absolute;
    z-index: 9999;
    top: 20vh;
    left: 10vw;
    height: 70vh;
    width: 80vw;
    margin: auto;
    padding: 0 0 10px;
    background: linear-gradient(lightblue, lightcyan);
  }
  .title-nav {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 10px;
    align-items: center;
    padding: 20px;
    position: relative;
    top: 1em;
    height: 4em;
    background: linear-gradient(lightblue, darkblue);
    border-radius: 10px;
    color: beige;
    justify-content: center;
  }
  .tab.active > .title-nav {
    top: 0;
    border-radius: 10px 10px 20px 20px;
  }
  .tab-title {
    font-size: 18px;
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow: 0 2px 4px lightcyan;
    cursor: pointer;
  }
  .tab-title.current {
    font-size: 24px;
    color: whitesmoke;
    padding: 10px 20px;
  }
  .close-btn {
    cursor: pointer;
    display: none;
    height: 40px;
    width: 40px;
  }
  .close-btn.active {
    display: block;
    float: right;
  }
  .tab-content {
    display: none;
  }
  .tab-content.active {
    display: block;
    height: 50vh;
    margin: 10px 0;
    overflow-y: auto;
  }
  @media screen and (max-width: 719px) {
    .tab {
      width: 100%;
      margin: 0 0 10px;
    }
    .tab.active {
      width: 100vw;
      left: 0;
    }
  }
</style>
