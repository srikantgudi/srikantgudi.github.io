<script>
import Panel from "./Panel.svelte";

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
	let selectedGroup = skills[0];
</script>

<style>
    .skills {
        display: grid;
        grid-template-columns: repeat(3, auto);
        overflow-y: auto;
        overflow-x: hidden;
        padding: 10px;
    }
    .skill-group {
        padding: 4px;
        font-size: 12px;
        cursor: pointer;
        font-family: Roboto;
    }
    .skill-group.active {
        color: white;
        justify-content: center;
        font-weight: 600;
        font-family: Montserrat;
        letter-spacing: 2px;
        font-size: 18px;
    }
    .skill {
        width: 20em;
        flex: 1;
    }
</style>
<Panel>
    <div slot="header">
        Technical Skills
    </div>
    <div slot="content">
        <div>
            <!-- <div class="skill-names">
                {#each skills as skill}
                    <div class="skill-name" class:active={selectedGroup === skill} 
                        on:click={() => selectedGroup = skill}>
                        {skill.group}
                    </div>
                {/each}
            </div>
            <div class="skills-detail">
                {#each selectedGroup.items as item}
                <div class="skill">
                    <div>{item.name}</div>
                    <svg height="40" width="200">
                        <rect x="0" y="10" height="30" width="150" fill="transparent" stroke="blue" />
                        <rect x="0" y="10" height="30" width={item.rating * 15} fill="darkslateblue" stroke="blue" />
                        <text x="80%" y="70%">{item.rating}/10</text>
                    </svg>
                </div>
                {/each}
            </div> -->
            {#each skills as skill}
            <Panel hdrbg="#666666" showcontent={selectedGroup===skill}>
                <div slot="header" on:click={() => selectedGroup=skill}>
                    <div class="skill-group" class:active={selectedGroup === skill} 
                        on:click={() => selectedGroup = skill}>
                        {skill.group}
                    </div>
                </div>
                <div slot="content">
                    <div class="skills">
                        {#each selectedGroup.items as item}
                            <div class="skill">
                                <div>{item.name}</div>
                                <svg height="40" width="200">
                                    <rect x="0" y="10" height="30" width="150" fill="transparent" stroke="blue" />
                                    <rect x="0" y="10" height="30" width={item.rating * 15} fill="darkslateblue" stroke="blue" />
                                    <text x="80%" y="70%">{item.rating}/10</text>
                                </svg>
                            </div>
                        {/each}
                    </div>
                </div>
            </Panel>
            {/each}
        </div>
    </div>
</Panel>