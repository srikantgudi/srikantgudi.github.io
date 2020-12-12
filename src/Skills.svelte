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
        display: block;
        height: 16em;
        padding: 10px;
    }
    .skill-names {
        display: flex;
        margin: 10px;
    }
    .skill-name {
        box-shadow: 0 0 4px #999999;
        padding: 4px;
        font-size: 12px;
        cursor: pointer;
        font-family: Orbitron;
    }
    .skill-name.active {
        background-color: darkslategrey;
        color: white;
        justify-content: center;
        font-weight: 600;
    }
    .skills-detail {
        display: flex;
        align-items: start;
        padding: 0 10px;
        flex-flow: row wrap;
        font-size: 14px;
        overflow-x: hidden;
        overflow-y: auto;
    }
    .skill {
        width: 20em;
        flex: 1;
    }
</style>
<div class="skills">
    <div class="skill-names">
        {#each skills as skill}
            <div class="skill-name" class:active={selectedGroup === skill} 
                on:mouseover={() => selectedGroup = skill}>
                {skill.group}
            </div>
        {/each}
    </div>
    <div class="skills-detail">
        {#each selectedGroup.items as item}
        <div class="skill">
            <div>{item.name}</div>
            <svg height="40" width="150">
                <rect x="0" y="10" height="30" width="150" fill="transparent" stroke="blue" />
                <rect x="0" y="10" height="30" width={item.rating * 15} fill="darkslateblue" stroke="blue" />
                <text x="190" y="10">{item.rating}/10</text>
            </svg>
        </div>
        {/each}
    </div>
</div>