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
		<div class="note">
			<small>Highlight over each section to see effect!</small>
		</div>
		<div class="resume">
			<Profile />
			<Skills />
			<WorkHistory />
		</div>
	</main>
</div>
