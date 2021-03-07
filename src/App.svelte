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
    <Profile />
    <Skills />
    <WorkHistory />
    <Academic />
  </main>
</div>
