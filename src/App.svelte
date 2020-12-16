<script>
	import Topnav from "./Topnav.svelte";
	import Profile from "./Profile.svelte";
	import Skills from "./Skills.svelte";
	import WorkHistory from "./WorkHistory.svelte";

	let profiles = [
		'Senior software professional with over 20 years of experience',
		'2005 - 2013: Web development experience using PHP, MySQL',
		'2014 onwards into UI development. Skills used Angular, React, Svelte, Stencil, NodeJs, MySql',
		'Can create wire-frames, POCs'
	];
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

<div class="container">
	<main class="main">
		<Topnav />
		<div style={{position: 'absolute',color:'#666666', fontStyle:'italic',fontFamily:'serif', top:'3em',left:'40%',right:'40%', height:'25px'}}>
			<small>Highlight over each section to see effect!</small>
		</div>
		<div class="resume">
			<Profile />
			<Skills />
			<WorkHistory />
		</div>
	</main>
</div>
