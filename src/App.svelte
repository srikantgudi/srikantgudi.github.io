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
				'Developed UI for a POC for Digital Readiness Analysis Tool to create a survey questionnaire for various categories using Angular, Material Design, HTML5, CSS3, JavaScript, API integration'
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

<style>
	* {
		margin: 0;
		font-family: Helvetica;
	}
	.bold {
		font-weight: 600;
	}
	#my-app {
		width: 96vw;
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
	.profile-title {
		position: fixed;
		z-index: 999;
		top: 20px;
		left: 30vw;
		width: 30vw;
		box-shadow: 0 0 4px #999999;
		padding: 10px;
		text-align: center;
		font-family: 'Trebuchet MS';
		font-size: 24px;
		background-color: navy;
		color: lightcyan;
		border-radius: 10px 10px 4px 4px;
	}
	.box {
		box-shadow: 0 4px 2px navy;
		border-radius: 0 0 4px 4px;
	}
	#name {
		grid-area: name;
	}
	#name .title {
		font-family: cursive;
		font-size: 30px;
		font-weight: 600;
		color: #00f;
		text-shadow: 1px 2px 2px lightblue;
	}
	#contact {
		grid-area: contact;
		text-align: right;
		line-height: 30px;
	}
	#contact .mail {
		text-decoration: none;
	}
	.profile, .skills {
		margin-bottom: 10px;
		border-radius: 0 0 4px 4px;
	}
	.content {
		display: grid;
		grid-template-columns: 1fr 2fr;
		grid-gap: 10px;
	}
	.left-panel {
	}
	.right-panel {
	}
	.workexp {
		box-shadow: 0 0 4px olive;
		margin-top: 10px;
	}
	.exp-hdr-title {
		box-shadow: 0 0 4px #999999;
		margin-bottom: 8px;
	}
	.org {
		font-weight: 600;
	}
	.exp {
		margin-bottom: 4px;
		display: block;
	}
	.exphdr {
		grid-area: exphdr;
		background-color: #def;
		padding: 4px 10px;
		font-size: 14px;
		font-weight: 600;
		cursor: pointer;
	}
	.exphdr.activehdr {
		box-shadow: 0 2px 8px #666;
		background-color: #666;
		color: lightcyan;
	}
	.expdetail {
		grid-area: expdetail;
		height: auto;
		margin: 0 0 8px;
		padding: 10px;
	}
	.activehdr, .section-title {
		background-color: lightblue;
		color: navy;
		padding: 4px 10px;
	}
	.section-title {
		margin-top: 4px;
	}
	.profile-content {
		padding: 10px;
	}
</style>

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
	<div class='content'>
		<div class="profile-title">Senior Frontend Engineer</div>
		<div class='left-panel'>
			<div class='profile box'>
				<h3 class='section-title'>Summary</h3>
				<div class='profile-content'>
					<ul>
					{#each profiles as line}
						<li>{line}</li>
					{/each}
					</ul>
				</div>
			</div>
			<div class='skills box'>
				<h3 class='section-title'>Skills</h3>
				<div class='profile-content'>
					<ul>
						{#each skills as skill}
							<li>{skill}</li>
						{/each}
					</ul>
				</div>
			</div>
		</div>
		<div class='right-panel'>
			<h3 class='section-title'>Experience</h3>
			<div class='workexp'>
				{#each expList as exp}
					<div class='exp' on:click={() => curExp = exp}>
						<div class='exphdr' class:activehdr={curExp === exp}>
							{exp.header.dates} :: {exp.header.jobTitle} - {exp.header.org}
						</div>
						{#if curExp === exp}
							<div class='expdetail'>
								<ul>
									{#each curExp.content as line}
										<li>{line}</li>
									{/each}
								</ul>
							</div>
						{/if}
					</div>
				{/each}
			</div>
		</div>
	</div>
</main>
