<svelte:head>
	<script type="text/javascript" src="https://platform.linkedin.com/badges/js/profile.js" async defer></script>
</svelte:head>

<script>
	import ResumeItem from "./ResumeItem.svelte";
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
		background: #eeeeee;
	}
	.appinfo-icon {
		position: absolute;
		top: 2em;
		right: 2em;
		font-style: italic;
		font-weight: 600;
		cursor: pointer;
	}
	.appinfo {
		position: absolute;
		top: 0.5em;
		right: 0;
		z-index: 999;
		display: none;
		transition: all 1s;
		width: 12em;
		padding: 4px 8px;
		background-color: darkslateblue;
		color: #f9f9f9;
		box-shadow: 0 0 4px whitesmoke;
		font-family: cursive;
		text-align: center;
	}
	.appinfo-icon:hover > .appinfo {
		display: block;
		transform: translate(1em,1em);
	}
	.page-title {
		font-family: Georgia;
		font-style: italic;
		text-shadow: 1px 2px 2px navy;
		font-size: 30px;
		font-weight: 600;
	}
	.resume {
		display: block;
	}
	:global(.card) {
        border-radius: 8px 8px 0 0;
		display: flex;
		font-size: 20px;
		box-shadow: 0 0 4px #999999;
		padding: 4px 10px;
		margin-bottom: 4px;
	}
	.skillsdetail {
		display: grid;
		grid-template-columns: 1fr;
		grid-gap: 2px 0;
	}
	.note {
		font-size: 12px;
		font-style: italic;
	}
</style>

<main>
	<div class="topnav box">
		<svg height="50" width="100%">
			<text x="50%" y="45%" text-anchor="middle" id="fullname" class="page-title">Srikant Gudi
				<animate attributename="fill" values="lightblue;blue;navy;blue;lightblue" begin="0" dur="10s" repeatcount="indefinite" />
			</text>
			<text x="50%" y="80%" text-anchor="middle" font-size="80%">
				Bengaluru, India | srikantgudi@gmail.com | +91-829-665-6336
			</text>
		</svg>
		<div class="appinfo-icon">
			[!]
			<div class="appinfo">
				This resume is developed using Svelte and SVG!
			</div>
		</div>
	</div>
	<div id="pos" class="box">
		<svg height="25" width="100%">
			<rect x="0" y="0" width="100%" height="100%" fill="lightcyan" />
			<text x="50%" y="70%" font-weight="bold" fill="darkslateblue" text-anchor="middle">
				Senior Frontend Professional
				<animate attributename="x" values="20%;60%;40%;80%;20%" begin="0" dur="10s" repeatcount="indefinite" />
			</text>
		</svg>
	</div>
	<div class="resume">
		<div>
			<ResumeItem showContent={opt===1}>
				<div slot="header" on:click={() => opt = 1}>
					Profile
				</div>
				<div slot="content">
					<Profile />
				</div>
			</ResumeItem>
			<ResumeItem showContent={opt===2}>
				<div slot="header" on:click={() => opt = 2}>
					Technical Skills <span class="note">(Click on each group to view details)</span>
				</div>
				<div slot="content">
				<!-- 	<div class="skillsdetail">
						{#each skills as item}
							<ResumeItem showContent={selectedGroup===item} hdrfntsize="14" hdrclr="blue" fntclr='olive' hdrbg="lightblue">
								<div slot="header" on:click={() => {selectedGroup=item}}>{item.group}</div>
								<div slot="content">
									{#each selectedGroup.items as skill}
										<svg height="70" width="300">
											<rect x="5" y="5" height="60" width="200" fill="transparent" stroke="blue" />
											<text x="30%" y="23" font-weight="600" fill="blue" text-anchor="middle">{skill.name}</text>
											<rect x="5" y="34" height="30" width="198" fill="#cccccc" />
											<rect x="6" y="34" height="30" width={skill.rating * 20} fill="#999" />
											<text x="210" y="50" font-size="14px">{skill.rating}/10</text>
										</svg>
									{/each}
								</div>
							</ResumeItem>
						{/each}
					</div>
				</div> -->
				<Skills />
			</ResumeItem>
			<ResumeItem showContent={opt===3}>
				<div slot="header" on:click={() => opt = 3}>
					Work Experience <span class="note">(Hover on the date to view details)</span>
				</div>
				<div slot="content">
					<WorkHistory />
				</div>
			</ResumeItem>
		</div>
	</div>
	
	<!-- <div class="skills">
		<figure>
			<figcaption>
				Technical Skills
			</figcaption>
			<div class="skills-content">
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
		</figure>
	</div>
	
	<div class="exp">
		<figure>
			<figcaption>
				Experience
			</figcaption>
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
		</figure>
	</div> -->
</main>
