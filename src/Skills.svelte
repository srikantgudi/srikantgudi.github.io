<script>
    let skills = [
		{
			group: 'Web Technologies',
			items: [
				{name: 'HTML5', rating: 8},
				{name: 'CSS3', rating: 8},
				{name: 'JavaScript', rating: 8},
			]
		},
		{
			group: 'Frameworks/ Libraries',
			items: [
				{name: 'Angular', rating: 8},
				{name: 'Svelte', rating: 8}, 
				{name: 'Stencil', rating: 6},
				{name: 'React', rating: 7},
				{name: 'Vue', rating: 7},
				{name: 'Nuxt', rating: 7},
			]
		},
		{
			group: 'Databases/ NoSQL',
			items: [
				{name: 'MySql', rating: 7},
				{name: 'Mongodb', rating: 6},
			]
		},
		{
			group: 'Others',
			items: [
				{name: 'Git/ Bitbucket', rating: 7},
				{name: 'Confluence', rating: 7},
				{name: 'Visual Studio Code', rating: 8},
				{name: 'IntelliJ', rating: 7}
			]
		}
	];
	let opt = 1;
	let selectedGroup = skills[0];
</script>

<style>
    .skills {
        display: grid;
        grid-template-columns: 1fr 3fr;
        grid-gap: 4px;
    }
    .skill-name {
        box-shadow: 0 0 4px #999999;
        padding: 4px;
        font-size: 18px;
        cursor: pointer;
    }
    .skill-name.active {
        background-color: darkslategrey;
        color: white;
        text-align: right;
        text-transform: uppercase;
    }
    .skill-name.active:after {
        content: '>>';
    }
    .skills-detail {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-gap: 4px;
    }
</style>
<div class="skills">
    <div>
        {#each skills as skill}
            <div class="skill-name" class:active={selectedGroup === skill} 
                on:click={() => selectedGroup = skill}>
                {skill.group}
            </div>
        {/each}
    </div>
    <div class="skills-detail">
        {#each selectedGroup.items as item}
        <svg height="60" width="300">
            <rect x="5" y="5" height="100" width="200" fill="transparent" stroke="blue" />
            <text x="30%" y="23" font-weight="600" fill="blue" text-anchor="middle">{item.name}</text>
            <rect x="5" y="30" height="100%" width="200" fill="#cccccc" />
            <rect x="5" y="30" height="100%" width={item.rating * 20} fill="darkslateblue" />
            <text x="210" y="45" font-size="14px">{item.rating}/10</text>
        </svg>
        {/each}
    </div>
</div>