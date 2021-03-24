<script>
	import SkillLevel from './SkillLevel.svelte';
	export let name;
	export let rating;
</script>
<div>
	<SkillLevel text={name} level={rating} />
</div>