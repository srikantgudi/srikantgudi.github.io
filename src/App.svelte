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
				Specialized in:
			</div>
			<div class="content-item">
				Svelte, VueJS, React, Angular, StencilJS, NodeJS
			</div>
			<div class="content-item">
				JavaScript, TypeScript, HTML5, CSS3, JSON, SVG
			</div>
			<div class="content-item">
				Familiar with: Python-Django, Laravel
			</div>
			<div class="content-item">
				srikantgudi@gmail.com | +91 829 665 6336
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