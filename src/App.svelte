<script>
  import Topnav from './Topnav.svelte'
  import Profile from './Profile.svelte'
  import Skills from './Skills.svelte'
  import WorkHistory from './WorkHistory.svelte'
  import Academic from './Academic.svelte'

  let opt = 1
</script>

<div class="container">
  <main class="main">
    <Topnav />
    <div class="resume">
      <div class="resumenav">
        <button
          class="sectiontitle link"
          class:active={opt === 1}
          on:click={() => {
            opt = 1
          }}>
          Profile
        </button>
        <button
          class="sectiontitle link"
          class:active={opt === 2}
          on:click={() => {
            opt = 2
          }}>
          Technical Skills
        </button>
        <button
          class="sectiontitle link"
          class:active={opt === 3}
          on:click={() => {
            opt = 3
          }}>
          Work History
        </button>
        <button
          class="sectiontitle link"
          class:active={opt === 4}
          on:click={() => {
            opt = 4
          }}>
          Academic
        </button>
      </div>
      <div class='resumecontent'>
        <Profile {opt} />
        <Skills {opt} />
        <WorkHistory {opt} />
        <Academic {opt} />
      </div>
    </div>
  </main>
</div>
