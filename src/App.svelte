<script>
  import {mainOpt} from './store';

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
    <Profile selected={$mainOpt === 'profile'} />
    <Skills selected={$mainOpt === 'skills'} />
    <WorkHistory selected={$mainOpt === 'exp'} />
    <Academic selected={$mainOpt === 'qual'} />
  </main>
</div>
