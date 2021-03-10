<script>
  import Topnav from "./Topnav.svelte";
  import Profile from "./Profile.svelte";
  import Profile2 from "./Profile2.svelte";
  import Skills from "./Skills.svelte";
  import WorkHistory from "./WorkHistory.svelte";
  import Academic from "./Academic.svelte";

  let contentId = 1;
</script>

<div id="app">
  <div class="topnav">
    <div class="topnav-title">Srikant Gudi</div>
    <div class="contact">
      <div class="contact-item">Bengaluru, India</div>
      <div class="contact-item">srikantgudi@gmail.com</div>
      <div class="contact-item">+91 829 665 6336</div>
    </div>
    <div class="position-title">Senior Frontend Engineer</div>
  </div>

  <div class="content">
    <div
      class="content-item"
      on:click={() => {
        contentId = 1;
      }}
      class:active={contentId === 1}
    >
      <div class="tab-btn">Profile</div>
      <div class="content-text" class:active={contentId === 1}>
        <Profile />
      </div>
    </div>
    <div
      class="content-item"
      on:click={() => {
        contentId = 2;
      }}
      class:active={contentId === 2}
    >
      <div class="tab-btn">Technical Skills</div>
      <div class="content-text" class:active={contentId === 2}>
        <Skills />
      </div>
    </div>
    <div
      class="content-item"
      on:click={() => {
        contentId = 3;
      }}
      class:active={contentId === 3}
    >
      <div class="tab-btn">Work History</div>
      <div class="content-text" class:active={contentId === 3}>
        <WorkHistory />
      </div>
    </div>
    <div
      class="content-item"
      on:click={() => {
        contentId = 4;
      }}
      class:active={contentId === 4}
    >
      <div class="tab-btn">Academic</div>
      <div class="content-text" class:active={contentId === 3}>
        <ul>
          <li>Master in Computer Management</li>
          <li>Bachelor of Commerce</li>
        </ul>
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
    background: linear-gradient(whitesmoke, #eef);
    height: 96vh;
  }

  .topnav {
    box-shadow: 0 0 4px #999;
    min-height: 4em;
    margin: 0 1em;
    padding: 10px;
    background: linear-gradient(lightblue, aliceblue, lightblue);
    border-radius: 0 0 10px 10px;
    display: flex;
    align-items: center;
    flex-flow: column;
    justify-content: center;
  }
  .topnav-title {
    font-family: Righteous;
    font-size: 28px;
    font-weight: 400;
    text-transform: uppercase;
    color: navy;
  }
  .contact {
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    justify-content: center;
    font-family: Montserrat;
    text-align: center;
  }
  .contact-item {
    min-width: 27vw;
    cursor: pointer;
  }
  .position-title {
    text-transform: uppercase;
    font-family: Orbitron;
    font-size: 24px;
    font-weight: 600;
    letter-spacing: 1px;
    text-align: center;
    color: blue;
  }
  .content {
    display: flex;
    align-items: center;
    margin: 10px 15px;
    gap: 10px;
  }
  .content-item {
    flex: 1;
    border-radius: 10px 10px 4px 4px;
    margin-top: 20px;
    padding: 0 20px;
    display: block;
    height: 50vh;
    overflow: hidden;
    cursor: pointer;
    box-shadow: 0 0 4px #999;
    transition: all 0.5s ease-in-out;
  }
  .content-item:hover {
    flex: 3;
    height: 70vh;
    margin-top: 0;
    overflow-y: auto;
    border-radius: 20px 20px 10px 10px;
    box-shadow: 0 2px 10px #666666;
  }
  .content-item:hover > .tab-btn {
    background-color: lightcyan;
    color: navy;
    border-radius: 20px 20px 4px 4px;
    font-family: Orbitron;
    font-size: 20px;
    text-align: center;
  }
  @media screen and (max-width: 719px) {
    #app {
      height: auto;
    }
    .position-title {
      font-size: 90%;
      font-weight: 600;
    }
    .content {
      flex-flow: column;
      align-items: flex-start;
      overflow-y: auto;
    }
    .content-item {
      width: 100%;
    }
  }
</style>
