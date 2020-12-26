<script>
    import Sklevel from './Sklevel.svelte';
		let name = 'Technical Skills';
		let skills = [
			{name: 'Angular', level: 8},
			{name: 'Svelte', level: 7},
			{name: 'VueJS', level: 7},
			{name: 'React', level: 7},
			{name: 'Stencil', level: 6},
			{name: 'NodeJS', level: 6},
			{name: 'JavaScript', level: 8},
			{name: 'HTML5', level: 8},
			{name: 'CSS3', level: 7},
			{name: 'MySQL', level: 7},
			{name: 'MongoDB', level: 6},
			{name: 'SVG', level: 5},
			{name: 'Python', level: 4},
		];
</script>


<div class="section">
    <div class="sectiontitle">
        Technical Skills
    </div>
    {#each skills as skill}
			<Sklevel text={skill.name} level={skill.level} />
		{/each}
</div>
