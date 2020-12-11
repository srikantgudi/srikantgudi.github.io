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
		'HTML5, CSS3, JavaScript',
		'Angular, Svelte, Stencil, React, Vue, Nuxt',
		'MySql, Mongodb',
		'Git, Bitbucket, Confluence'
	];
	let opt = 1;
</script>

<style>
	:root {
		background: #eeeeee;
	}
	.appinfo-icon {
		position: absolute;
		top: 2em;
		right: 20em;
		font-style: italic;
		font-weight: 600;
		cursor: pointer;
	}
	.appinfo {
		position: absolute;
		top: 0.5em;
		left: 0;
		z-index: 999;
		display: none;
		transition: all 1s;
		width: 12em;
		padding: 4px 8px;
		background-color: darkslateblue;
		color: #f9f9f9;
		box-shadow: 0 0 4px whitesmoke;
	}
	.appinfo-icon:hover > .appinfo {
		display: block;
		transform: translate(1em,1em);
	}
	.info {
		display: grid;
		grid-template-columns: 1fr 1fr;
		box-sizing: border-box;
		padding: 20px;
		border-radius: 20px 20px 4px 4px;
		box-shadow: 0 0 4px #999999;
		background: linear-gradient(#eeeeee, #cccccc);
		transition: all 1s;
		clear: both;
	}
	.info-title {
		font-family: Georgia;
		font-style: italic;
		text-shadow: 1px 2px 2px navy;
		font-size: 30px;
		font-weight: 600;
	}
	.info-contact {
		text-align: right;
	}
	.info-pos {
		position: absolute;
		top: 4em;
		left: 15%;
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
</style>

<main>
	<div class="info">
		<div>
			<div class='info-title'>SRIKANT GUDI</div>
			<div>Bengaluru, India</div>
		</div>
		<div class="info-contact">
			<div>srikantgudi@gmail.com</div>
			<div>+91-892-665-6336</div>
			<div class="appinfo-icon">
				[!]
				<div class="appinfo">
					This resume is developed using Svelte and SVG for graph!
				</div>
			</div>
		</div>
	</div>
	<div class="info-pos">
		<svg height="40" width="70vw">
			<text x="32%" y="25" font-family="Trebuchet MS" font-weight="600" font-size="24px">
				Senior Frontend Engineer
				<animate attributename="fill" values="lightblue;blue;navy;blue;lightblue" dur="10s" begin="0" repeatcount="indefinite" />
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
					Technical Skills
				</div>
				<div slot="content">
					<Skills />
				</div>
			</ResumeItem>
			<ResumeItem showContent={opt===3}>
				<div slot="header" on:click={() => opt = 3}>
					Work Experience
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
