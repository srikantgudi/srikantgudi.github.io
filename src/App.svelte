<script>
	let profiles = [
		'Senior software professional with over 20 years of experience',
	  '2005 - 2013: Web development experience using PHP, MySQL',
	  '2014 onwards into UI development',
	  'Can create wire-frames, POCs'
	];
	let skills = [
		'HTML5, CSS3, JavaScript',
		'Angular, Svelte, Stencil, React, Vue, Nuxt',
		'MySql, Mongodb',
		'Git, Bitbucket, Confluence'
	];
	let opt = 1;

	let expList = [
		{
			header: {
				dates: '16-Jun-2016 to present',
				jobTitle: 'Project Lead - System',
				org: 'Mphasis, Bengaluru',
			},
			content: [
				'Worked offshore in Bengaluru with a banking conglomerate on  projects in Angular and React',
				'Worked onsite in Glasgow, UK with a banking conglomerate on Angular based projects',
				'Worked offshore at client-side with Schneider Electric on Management Dashboard using Angular 1.x',
				'Developed UI for a POC for Digital Readiness Analysis Tool to created a survey questionnaire for various categories using Angular, Material Design, HTML5, CSS3, JavaScript, API integration'
			]
		},
		{
			header: {
				dates: '15-Aug-2015 to 14-Jan-2016',
				jobTitle: 'Senior AngularJS Developer',
				org: 'Pandera Solutions India Pvt Ltd, Bengaluru',
			},
			content: [
				'Worked in Angular on various projects',
				'Created sub-components for re-use',
				'Interacted with client-side developers to understand the requirements',
				'Integrated APIs in the frontend code'
			]
		}
	];
	let curExp = expList[0];
</script>

<main id="my-app">
	<div id="top-nav">
		<div id='name'>
			<div class='title'>
				Srikant Gudi
			</div>
			<div>
				Bengaluru, India
			</div>
		</div>
		<div id='contact'>
			<div class="mail">srikantgudi@gmail.com</div>
			<div>+91 829-665-6336</div>
		</div>
	</div>
	<div id="profile">
		<div class='box'>
			<h3>Summary</h3>
			<ul>
			{#each profiles as line}
				<li>{line}</li>
			{/each}
			</ul>
		</div>
		<div class='box'>
			<h3>Skills</h3>
			{#each skills as skill}
				<li>{skill}</li>
			{/each}
		</div>
	</div>
	<h3>Experience</h3>
	<div id='workexp'>
		<div class='exp-left'>
			{#each expList as exp}
				<div on:click={() => curExp = exp} class='exp-hdr-title'>{exp.header.org}</div>
			{/each}
		</div>
		<div class='exp-detail'>
			<div class='exp'>
				<div class='exphdr'>
					{curExp.header.dates} :: {curExp.header.jobTitle} - {curExp.header.org}
				</div>
				<div class='expcontent'>
					<ul>
						{#each curExp.content as line}
							<li>{line}</li>
						{/each}
					</ul>
				</div>
			</div>
		</div>
	</div>
</main>
<style>
	* {
		margin: 0;
		font-family: Helvetica;
	}
	.expactive {
		display: block;
		background-color: #def;
	}
	.exphide {
		display: none;
	}
	.bold {
		font-weight: 600;
	}
	#my-app {
		width: 90vw;
		margin: 0 auto;
		font-family: Helvetica;
	}
	#top-nav {
		box-shadow: 0 0 4px #999999;
		padding: 4px 10px;
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-gap: 10px;
		grid-template-areas: 'name contact';
		background-color: #eeeeee;
	}
	.box {
		box-shadow: 0 0 4px #999999;
	}
	#name {
		grid-area: name;
	}
	#name .title {
		font-family: cursive;
		font-size: 30px;
		font-weight: 600;
	}
	#contact {
		grid-area: contact;
		text-align: right;
		line-height: 30px;
	}
	#contact .mail {
		text-decoration: none;
	}
	#profile {
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-gap: 20px;
		margin: 10px auto;
	}
	#profile > div {
		padding: 8px 20px;
	}
	#workexp {
		box-shadow: 0 0 2px #333333;
		display: grid;
		grid-template-columns: 30vw 1fr;
		height: 32vw;
	}
	.exp-left {
		border-right: 1px solid #dddddd;
		height: inherit;
		overflow-y: auto;
	}
	.exp {
		display: grid;
		grid-template-rows: 40px 2fr;
		grid-template-areas: 'exphdr'
		'expcontent';
		grid-gap: 4px;
		margin: 10px auto;
		font-size: 14px;
	}
	.exp-hdr-title {
		border-bottom: 1px solid #cccccc;
		padding: 8px;
	}
	
	.exphdr {
		padding: 8px;
		box-shadow: 0 0 4px #999999;
	}
	.exp-detail {
		padding: 10px;
	}
	.expcontent {
		grid-area: expcontent;
		padding: 8px;
		font-size: 16px;
		transition: all 1s;
		height: inherit;
		overflow-y: auto;
	}

</style>
