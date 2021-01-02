<script>
	import Topnav from "./Topnav.svelte";
	import Profile from "./Profile.svelte";
	import Skills from "./Skills.svelte";
	import WorkHistory from "./WorkHistory.svelte";

  let opt = 1
	let menuitems = {
		"Profile": Profile,
		"Technical Skills": Skills,
		"Work History": WorkHistory
	}
	let comp = menuitems['Profile'];
</script>

<div class="container">
	<main class="main">
		<Topnav />
		<div class="note">
			Highlight over each section to see effect!
		</div>
		<div class="resume">
			<div class="navmenu">
				{#each Object.keys(menuitems) as key}
				<div class="menuitem" on:click={() => comp = menuitems[key]} class:active={comp === menuitems[key]}>{key}</div>
				{/each}
		</div>
		<svelte:component this={comp} />
		</div>
	</main>
</div>
