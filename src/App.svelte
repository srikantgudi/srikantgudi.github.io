<script>
	import Topnav from "./Topnav.svelte";
	import Profile from "./Profile.svelte";
	import Skills from "./Skills.svelte";
	import WorkHistory from "./WorkHistory.svelte";

  let opt = 1
</script>

<div class="container">
	<main class="main">
		<Topnav />
		<div style={{position: 'absolute',color:'#666666', fontStyle:'italic',fontFamily:'serif', top:'3em',left:'40%',right:'40%', height:'25px'}}>
			<small>Highlight over each section to see effect!</small>
		</div>
		<div class="resume">
			<Profile />
			<Skills />
			<WorkHistory />
		</div>
	</main>
</div>
