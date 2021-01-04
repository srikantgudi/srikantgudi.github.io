<script>
	import Stars from './Stars.svelte';
  import Panel from './Panel.svelte';
  import Profile from './Profile.svelte';
  import Skills from './Skills.svelte';
  import WorkHistory from './WorkHistory.svelte';
</script>

<main>
  <Panel>
    <div slot="title">SRIKANT GUDI</div>
    <div slot="subtitle">
      <div>Bengaluru, India | srikantgudi@gmail.com | +91-829-665-6336</div>
      <div class="pos">SENIOR FRONT-END PROFESSIONAL</div>
    </div>
  </Panel>
	<div class="subtitle txtcenter">Best viewed in Landscape mode or in Chrome, FireFox and Edge</div>
  <Profile />
  <Skills />
  <WorkHistory />
</main>
