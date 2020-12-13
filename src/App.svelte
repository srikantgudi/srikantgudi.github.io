<svelte:head>
	<script type="text/javascript" src="https://platform.linkedin.com/badges/js/profile.js" async defer></script>
</svelte:head>

<script>
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

<style>
	:root {
		background: #666666;
	}
	:html {
		width: auto!important;
	}
	.info {
		text-align: center;
	}
	.appinfo-icon {
		position: absolute;
		top: 1em;
		right: 3em;
		font-style: italic;
		font-weight: 600;
		cursor: pointer;
	}
	.appinfo {
		position: absolute;
		top: 1em;
		right: 1em;
		z-index: 999;
		display: none;
		transition: all 1s;
		width: 12em;
		padding: 4px 8px;
		background-color: darkslateblue;
		color: #f9f9f9;
		box-shadow: 0 0 4px whitesmoke;
		font-family: Righteous;
	}
	.appinfo-icon:hover > .appinfo {
		display: block;
		transform: translate(-1em,1em);
	}
	:global(.page-title) {
		font-family: Righteous;
		font-style: italic;
		text-shadow: 1px 2px 2px navy;
		font-size: 30px;
		font-weight: 600;
	}
	.resume {
		position: absolute;
		top: 9em;
		left: 1em;
		right: 1em;
		display: grid;
		padding: 1em;
		grid-template-columns: 1fr 3fr;
		background-color: aliceblue;
	}
	.card {
        border-radius: 8px 8px 0 0;
		display: flex;
		font-size: 20px;
		box-shadow: 0 0 4px #999999;
		padding: 4px 10px;
		margin-bottom: 4px;
	}
	.card.active {
		background-color: lightblue;
		justify-content: right;
		font-weight: 600;
	}
	.card.active:after {
		content: '\20\bb';
		padding-right: 10px;
	}
	.topnav {
		position: fixed;
		z-index: 999;
		left: 0;
		top: 0;
		right: 0;
		background-color: aliceblue;
		width: auto;
		padding: 10px;
	}
	#pos {
		font-weight: 600;
		fill: blue;
		font-family: Righteous;
		font-size: 20px;
	}
	#contact {
		font-family: Ubuntu;
		font-size: 12px;
	}
	#fullname {
		text-transform: uppercase;
	}

	:global(.sectiontitle) {
		font-size: 20px;
		height: auto;
	}
	:global(.subtitle) {
		font-size: 14px;
		height: auto;
	}
</style>

<main>
	<div class="topnav box">
		<div class="info">
			<svg height="50" width="100%">
				<text x="50%" y="60%" text-anchor="middle" class="page-title" id="fullname">Srikant Gudi</text>
				<text x="50%" text-anchor="middle" y="90%" id="contact">Bengaluru, India | srikantgudi@gmail.com | +91-829-665-6336</text>
			</svg>
			<div id="pos" class="box">
				<svg height="25" width="100%">
					<rect x="0" y="0" width="100%" height="100%" fill="lightcyan" />
					<text id="pos" x="50%" y="70%"  fill="blue" font-weight="600" text-anchor="middle">
						Senior Frontend Professional
						<animate attributeName="fill" values="lightblue;blue;navy;orange;navy;blue;lightblue" begin="0" dur="5s" repeatCount="indefinite" />
					</text>
				</svg>
			</div>
		</div>
		<div class="appinfo-icon">
			<svg height="60" width="60">
				<circle r="15" cx="30" cy="30" fill="lightblue">
				</circle>
				<text x="25" y="38" fill="lightcyan" font-size="20px">
					!
					<animate attributeName="fill" values="navy;blue;lightcyan;blue;navy" begin="0" dur="5s" repeatCount="indefinite" />
				</text>
			</svg>
			<div class="appinfo">
				This resume is developed using Svelte and SVG!
			</div>
		</div>
	</div>
	<div class="resume">
		<div>
			<div class="card" class:active={opt === 1} on:click={() => opt = 1}>Profile</div>
			<div class="card" class:active={opt === 2} on:click={() => opt = 2}>Technical Skills</div>
			<div class="card" class:active={opt === 3} on:click={() => opt = 3}>Work Experience</div>
		</div>
		<div>
			{#if opt===1}
				<Profile />
			{/if}
			{#if opt===2}
				<Skills />
			{/if}
			{#if opt===3}
				<WorkHistory />
			{/if}
		</div>
	</div>
</main>
