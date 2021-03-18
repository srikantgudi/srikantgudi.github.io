<script>
	import Stars from './Stars.svelte';
	export let group;
	export let ratings = [];
</script>
<style>
	.skill {
		display: grid;
		grid-template-columns: 30% auto;
		gap: 10px;
	}
	.skillname {
		text-align: right;
	}
</style>
<h3>
	{group}
</h3>
{#each ratings as skill}
<div class="skill">
	<div class="skillname">{skill.name}</div>
	<div>
		<Stars val={skill.rating} />
	</div>
</div>
{/each}