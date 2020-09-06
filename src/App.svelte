<script>
let profiles = [
		'Senior software professional with over 20 years of experience',
	  '2005 - 2013: Web development experience using PHP, MySQL',
	  '2014 onwards into UI development. Skills used Angular, React, Svelte, Stencil, NodeJs, MySql',
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
		},
		{
			header: {
				dates: '20-Aug-2014 to 22-Jan-2015',
				jobTitle: 'Senior Software Developer',
				org: 'Basil Communications Pvt Ltd, Bengaluru',
			},
			content: [
				'Created HTML mockups for various applications',
				'Interacted with designers to understand the designs',
				'Used Photoshop to slice images'
			]
		}
	];
	let curExp = expList[0];
</script>

<style>
	:root {
		background: #adf;
	}
	.info {
		box-sizing: border-box;
		position: absolute;
		top: 1vh;
		left: 30vw;
		width: 40vw;
		border-radius: 20px 20px 4px 4px;
		padding: 20px 30px;
		box-shadow: 0 0 4px #999999;
		background: linear-gradient(#0ef, #dff);
		text-align: center;
		transition: all 1s;
	}
	.info:hover {
		z-index: 999;
		box-shadow: 0 4px 20px #f9f9f9;
		border-radius: 20px;
	}
	.info-title {
		font-family: Georgia;
		font-style: italic;
		text-shadow: 1px 2px 2px navy;
		font-size: 30px;
		font-weight: 600;
	}
	.section-title {
		background-color: #009;
		color: #ffa;
		padding: 10px 20px;
		border-radius: 2px 2px 10px 10px;
		font-size: 20px;
		font-weight: 600;
	}
	.profile {
		position: absolute;
		top: 14vh;
		left: 5vw;
		height: 30vh;
		width: 50vw;
		padding: 20px;
		border-radius: 20px 20px 8px 8px;
		background-color: #def;
		color: #666;
		box-shadow: 0 0 4px #999999;
		transition: all 1s;
	}
	.profile .text {
		color: #333333;
		font-size: 20px;
	}
	.profile:hover {
		z-index: 9999;
		box-shadow: 0 4px 20px #333333;
		border-radius: 25px 25px 40px 40px;
	}
	.skills {
		position: absolute;
		top: 14vh;
		right: 5vw;
		min-height: 32vh;
		width: 36vw;
		padding: 20px;
		border-radius: 20px 20px 8px 8px;
		background-color: #def;
		color: #666;
		box-shadow: 0 0 4px #999999;
		transition: all 1s;
	}
	.skills .content {
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-gap: 4px;
	}
	.skills:hover {
		z-index: 9999;
		box-shadow: 0 4px 20px #333333;
		border-radius: 25px 25px 40px 40px;
	}
	.exp {
		position: absolute;
		top: 24vh;
		left: 8vw;
		height: 66vh;
		width: 80vw;
		padding: 20px;
		border-radius: 20px 20px 8px 8px;
		background-color: #def;
		color: #666;
		box-shadow: 0 4px 20px #333333;
		transition: all 1s;
	}
	.exp:hover {
		border-radius: 25px 25px 50px 50px;
		background-color: lightcyan;
	}
	.exp-box {
		display: grid;
		grid-template-rows: auto 1fr;
		grid-gap: 2px;
		transition: all 1s;
	}
	.exp-box:hover {
		border-radius: 20px;
		background-color: #cccccc;
		padding: 10px 30px;
		box-shadow: 0 2px 20px #009;
	}
	.exphdr {
		background-color: #999999;
		color: #f7f7f7;
		padding: 4px 10px;
		font-size: 14px;
		cursor: pointer;
		transition: all 1s;
	}
	.exp-box:hover > .exphdr {
		color: blue;
		background-color: #ffa;
		border-radius: 10px 10px 0 0;
	}
	.exp-box:hover > .expdetail {
		border-radius: 0 0 15px 15px;
	}
	.expdetail {
		background-color: #eeeeee;
		color: #333333;
		padding: 4px 10px;
		font-size: 14px;
	}
	.bold {
		font-weight: 600;
	}
</style>

<main>
	<div class="info">
		<div class='info-title'>SRIKANT GUDI</div>
		<div>Bengaluru, India</div>
		<div>srikantgudi@gmail.com | +91-892-665-6336</div>
		<h1>Senior Frontend Engineer</h1>
	</div>
	<div class="profile">
		<div class="section-title">
			Profile
		</div>
		<ul class='text'>
			{#each profiles as line}
				<li>{line}</li>
			{/each}
		</ul>
	</div>
	
	<div class="skills">
		<div class="section-title">
			Technical Skills
		</div>
		<div class="content">
			<div>
				<ul class="bold">
					<li>Angular</li>
					<li>Svelte</li>
					<li>Stencil</li>
					<li>React</li>
					<li>Vue</li>
					<li>Nuxt</li>
				</ul>
				<ul>
					<li>Bootstrap</li>
					<li>Angular Material</li>
					<li>Material-UI</li>
					<li>Vuetify</li>
					<li>Buefy</li>
				</ul>
			</div>
			<div>
				<ul>
					<li>JavaScript</li>
					<li>HTML5</li>
					<li>CSS3</li>
					<li>NodeJS</li>
					<li>MySql</li>
					<li>Mongodb</li>
				</ul>
				<ul>
					<li>Git</li>
					<li>Bitbucket</li>
					<li>Confluence</li>
					<li>Visual Studio Code</li>
					<li>IntelliJ</li>
				</ul>
			</div>
		</div>
	</div>
	
	<div class="exp">
		<div class="section-title">
			Experience
		</div>
		<div>
			{#each expList as exp}
				<div class='exp-box' on:mouseover={() => curExp = exp}>
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

</main>
