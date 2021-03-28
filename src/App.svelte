<script>
	import Info from './Info.svelte';
	import Contact from './Contact.svelte';
	import Profile from './Profile.svelte';
	import Skills from './Skills.svelte';
	import WorkHistory from './WorkHistory.svelte';
	let name = 'world';
	
	let pages = [
		{'title': '', comp: Info},
		{'title': 'PROFILE', comp: Profile},
		{'title': 'TECHNICAL SKILLS', comp: Skills},
		{'title': 'WORK EXPERIENCE', comp: WorkHistory}
	];
</script>

<div class="resume">
	<Info />
	<Contact />
	<Profile />
	<Skills />
	<WorkHistory />
</div>