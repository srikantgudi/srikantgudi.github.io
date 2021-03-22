<script>
	import Info from './Info.svelte';
	import Profile from './Profile.svelte';
	import Skills from './Skills.svelte';
	import WorkHistory from './WorkHistory.svelte';
	let name = 'world';
	
	let pages = [
		{'title': 'INFO', comp: Info},
		{'title': 'PROFILE', comp: Profile},
		{'title': 'TECHNICAL SKILLS', comp: Skills},
		{'title': 'WORK EXPERIENCE', comp: WorkHistory}
	];
	let current = 0, lastPage = pages.length - 1;
	
	const goPage = (n) => {
		current += n
		if (current < 0) {
			current = lastPage
		} else if (current > lastPage) {
			current = 0
		}
	}
</script>

<div class="resume">
	<div class="btnnav">
		<button class="nav-btn" on:click={() => {goPage(-1)}}>
			&laquo;
		</button>
		<button class="nav-btn" on:click={() => {goPage(1)}}>
			&raquo;
		</button>
	</div>
	<div class="sectiontitle">
		{pages[current].title}
	</div>
	<div class="current">
		<svelte:component this={pages[current].comp} />
	</div>
	<div class="btnnav">
		
	</div>
</div>