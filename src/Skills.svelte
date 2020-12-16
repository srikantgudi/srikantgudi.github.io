<script>
    import Rategraph from './Rategraph.svelte';

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
	let groupId = 0;

	const setGroupId = (n) => {
		groupId = n;
	}
</script>


<div class="section">
    <div class="sectiontitle">
        Technical Skills
    </div>
    <div class="skillgroups">
        {#each skills as skill, idx}
            <div class="skillgroup">
                <div class="groupname" 
                on:click={() => {setGroupId(idx);}}>
                    {skill.group}
                </div>
                {#if groupId === idx}
                    <div class="skillslist">
                        {#each skill.items as item}
                            <div class="skill">
                                <span class="txtright">
                                    {item.name}: ({item.rating} / 10)
                                </span>
                                <span><Rategraph rating={item.rating} /></span>
                            </div>
                        {/each}
                    </div>
                {/if}
            </div>
        {/each}
    </div>
</div>
