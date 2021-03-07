<script>
  import Master from './Master.svelte'
  import Topnav from './Topnav.svelte'
  import Profile from './Profile.svelte'
  import Skills from './Skills.svelte'
  import WorkHistory from './WorkHistory.svelte'
  import Academic from './Academic.svelte'

  let comp = Profile
  let opt = 1
</script>

<div class="container">
  <main class="main">
    <Topnav />
    <div class="resume">
      <div class="resumenav">
        <button
          class="resume-tab-title link"
          class:active={comp === Profile}
          on:click={() => {
            comp = Profile
          }}>
          Profile
        </button>
        <button
          class="resume-tab-title link"
          class:active={comp === Skills}
          on:click={() => {
            comp = Skills
          }}>
          Skills
        </button>
        <button
          class="resume-tab-title link"
          class:active={comp === WorkHistory}
          on:click={() => {
            comp = WorkHistory
          }}>
          Work History
        </button>
        <button
          class="resume-tab-title link"
          class:active={comp === Academic}
          on:click={() => {
            comp = Academic
          }}>
          Academic
        </button>
      </div>
      <div class="resumecontent">
        <svelte:component this={comp} />
      </div>
    </div>
  </main>
</div>
