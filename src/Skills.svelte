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

<style>
  dl.skills {
    display: flex;
    flex-direction: column;
    width: 20em;
    box-shadow: 0 2px 4px #999999;
    margin-bottom: 2em;
  }
dt {
  font-weight: bold;
  background-color: skyblue;
  padding: 4px;
}
li {
  list-style: square;
}
</style>

<dl class="skills">
	{#each skills as skill}
		<dt>{skill.group}</dt>
		<dd>
			{#each skill.items as item}
				<li>
					<svg height="30" width="100">
						<rect x="0" y="0" height="100%" width="100%" fill="lightgrey"/>
						<rect x="0" y="0" height="100%" width={item.rating * 10} fill="grey"/>
					</svg>
					{item.name}
			</li>
			{/each}
		</dd>
	{/each}
</dl>
