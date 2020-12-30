<script>
	import Profile from './Profile.svelte'
	import Skills from './Skills.svelte'
	let comps = [
		{key: 'Profile', comp: Profile},
		{key: 'Skills', comp: Skills}
	]
	let comp = comps['Profile']
</script>

{#each comps as c}
	<button on:click={() => comp = c.comp}>{c.key}</button>
{/each}
<svelte:component this={comp} />
