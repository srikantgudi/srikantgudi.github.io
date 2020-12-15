<script>
  import Profile from './Profile.svelte'
  import Skills from './Skills.svelte'
  import WorkHistory from './WorkHistory.svelte'

  let opt = 1
</script>

<style>
  :root {
    background: #666666;
    overflow: hidden;
  }
  :html {
    background-color: aliceblue;
  }
  .info {
    text-align: center;
  }
  .appinfo-icon {
    position: absolute;
    top: 1em;
    right: 3em;
    font-style: italic;
    font-weight: 600;
    cursor: pointer;
  }
  .appinfo {
    position: absolute;
    top: 1em;
    right: 1em;
    z-index: 999;
    display: none;
    transition: all 1s;
    width: 12em;
    padding: 4px 8px;
    background-color: darkslateblue;
    color: #f9f9f9;
    box-shadow: 0 0 4px whitesmoke;
    font-family: Righteous;
  }
  .appinfo-icon:hover > .appinfo {
    display: block;
    transform: translate(-1em, 1em);
  }
  .resume {
    box-sizing: border-box;
    position: absolute;
    top: 9em;
    left: 1em;
    right: 1em;
    display: flex;
    flex-flow: row wrap;
    padding: 1em;
    height: 75vh;
    overflow-y: auto;
    background-color: aliceblue;
  }
  .section {
    box-sizing: border-box;
    flex: 1;
    min-width: 300px;
    margin: 0 10px 0 0;
    transition: all 0.5s ease-in;
    color: #999;
    padding: 10px;
    max-height: 32em;
    overflow: hidden;
    box-shadow: 0 0 2px #999999;
  }
  .section.active {
    flex: 3;
    overflow-y: auto;
    color: #333;
    box-shadow: 0 2px 6px #666666;
  }
  .topnav {
    position: fixed;
    z-index: 999;
    left: 0;
    top: 0;
    right: 0;
    background-color: aliceblue;
    width: auto;
    padding: 10px;
  }
  #pos {
    font-weight: 600;
    fill: blue;
    font-family: Righteous;
    font-size: 20px;
  }
  #contact {
    font-family: Ubuntu;
    font-size: 12px;
  }
  #fullname {
    text-transform: uppercase;
  }
  @media screen and (max-width: 1024px) {
    :root {
      font-size: 0.8;
      overflow-y: auto;
    }
    .resume {
      height: 100%;
      overflow-y: auto;
    }
    .section {
      overflow-y: auto;
    }
  }
</style>

<main>
  <div class="topnav box">
    <div class="info">
      <svg height="50" width="100%">
        <text
          x="50%"
          y="60%"
          text-anchor="middle"
          class="page-title"
          id="fullname">
          Srikant Gudi
        </text>
        <text x="50%" text-anchor="middle" y="90%" id="contact">
          Bengaluru, India | srikantgudi@gmail.com | +91-829-665-6336
        </text>
      </svg>
      <div id="pos" class="box">
        <svg height="25" width="100%">
          <rect x="0" y="0" width="100%" height="100%" fill="lightcyan" />
          <text
            id="pos"
            x="50%"
            y="70%"
            fill="blue"
            font-weight="600"
            text-anchor="middle">
            Senior Frontend Professional
            <animate
              attributeName="fill"
              values="lightblue;blue;navy;orange;navy;blue;lightblue"
              begin="0"
              dur="5s"
              repeatCount="indefinite" />
          </text>
        </svg>
      </div>
      <div>
        <small>Hover the below sections to expand!</small>
      </div>
    </div>
    <div class="appinfo-icon">
      <svg height="60" width="60">
        <circle r="15" cx="30" cy="30" fill="lightblue" />
        <text x="25" y="38" fill="lightcyan" font-size="20px">
          !
          <animate
            attributeName="fill"
            values="navy;blue;lightcyan;blue;navy"
            begin="0"
            dur="5s"
            repeatCount="indefinite" />
        </text>
      </svg>
      <div class="appinfo">This resume is developed using Svelte and SVG!</div>
    </div>
  </div>
  <div class="resume">
    <div
      class="section"
      class:active={opt === 1}
      on:mouseover={() => (opt = 1)}>
      <Profile />
    </div>
    <div
      class="section"
      class:active={opt === 2}
      on:mouseover={() => (opt = 2)}>
      <Skills />
    </div>
    <div
      class="section"
      class:active={opt === 3}
      on:mouseover={() => (opt = 3)}>
      <WorkHistory />
    </div>
  </div>
</main>
