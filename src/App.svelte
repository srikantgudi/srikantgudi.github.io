<script>
  	import {data} from './data/data';
	import Profile from './Profile.svelte';
	import TechSkills from './TechSkills.svelte';
	import WorkHistory from './WorkHistory.svelte';
</script>

<style>
</style>

<div class="resume">
	<div>
		<div class="topnav">
			<div class="title">
				SRIKANT GUDI
			</div>
			<div class="positiontitle">
				Senior FrontEnd Professional
			</div>
			<div class="content-item">
				srikantgudi@gmail.com
			</div>
			<div class="content-item">
					+91 829 665 6336
			</div>
		</div>
		<Profile />
	</div>
	<div>
		<div>
			<TechSkills />
		</div>
		<div>
			<WorkHistory />
		</div>
	</div>
</div>