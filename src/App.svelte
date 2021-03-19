<script>
	import { data } from './data/data.js'
	const winResize = e => {
		console.log('win-resize: e', e);
	}
	let showInfo = false;
</script>
<style>
	#app {
		width: 80vw;
		height: 94vh;
		margin: 0 auto;
		padding: 10px;
		background: linear-gradient(#023e8a,#00b4d8,#023e8a);
		color: navy;
		line-height: 1.2;
		font-family: Montserrat;
	}
	.page-header {
		display: flex;
		flex-flow: column;
		text-align: center;
		min-height: 10vh;
		width: 80vw;
		margin: 0 auto;
		border-radius: 20px 20px 0 0;
		margin-bottom: 10px;
		box-shadow: 0 4px 10px #999;
		border-radius: 20px 20px 10px 10px;
		color: #f5f3f4;
	}
	.name {
		font-family: Righteous;
		font-size: 24px;
		letter-spacing: 2px;
	}
	.positiontitle {
		font-size: 20px;
		font-family: Ubuntu;
		font-weight: 600;
		padding: 1vh 2vw;
		margin: 1vh 4vw;
		background: linear-gradient(#343a40,#dee2e6,#343a40);
		color: #161a1d;
		border-radius: 1em;
		animation: animPositionTitle 5s ease-in-out infinite reverse;
	}
	.panel {
		border-radius: 20%;
		box-shadow: 0 0 4px #999;
		height: 15vh;
		overflow: hidden;
		width: 50vw;
		margin: 8px auto;
		transition: all 0.5s;
	}
	.panel-header {
		font-family: Orbitron;
		position: relative;
		top: 6vh;
		font-size: 1vw;
		text-align: center;
		transition: all 1s;
		background-color: #999;
		border-radius: 10px;
		color: #f9f9f9;
		padding: 10px;
	}
	.panel-content {
		opacity: 0.2;
		font-size: 10px;
		font-family: Montserrat;
		color: #f5f3f4;
	}
	.panel:hover {
		border-radius: 10px;
		width: 70vw;
		height: 40vh;
		overflow-y: hidden;
		box-shadow: 0 4px 10px #009;
	}
	.panel:hover > .panel-header {
		letter-spacing: 3px;
		font-size: 1.5vw;
		font-weight: 600;
		top: 0;
		border-radius: 10px 10px 0 0;
		color: beige;
		background: linear-gradient(lightblue,blue);
	}
	.panel:hover > .panel-content {
		opacity: 1;
		font-size: 16px;
	}
	.panel:hover * .skills {
		overflow-y: auto;
	}
	.panel-inner {
		height: 30vh;
		overflow-y: unset;
	}
	.panel:hover * .panel-inner {
		overflow-y: auto;
	}
	.list {
		padding: 10px 20px;
	}
	.skills {
		display: grid;
		grid-template-columns: 1fr 1fr 1fr 1fr;
		font-family: Roboto;
		font-size: 14px;
		padding: 10px;
		font-family: Montserrat;
		height: 30vh;
		overflow-y: hidden;
	}
	.skill {
		transition: all 1s;
		min-width: 22%;
		box-shadow: 0 0 4px #999;
		text-align: center;
		padding: 4px;
		margin: 0 4px 4px 0;
		font-size: 18px;
		border-radius: 4px;
	}
	.exp {
		display: flex;
		flex-flow: column;
		padding: 10px;
	}
	.expdetail {
		padding: 10px;
		text-align: left;
		margin-left: 5vw;
    	font-family: Ubuntu;
	}
	.expdetail > .details {
		display: flex;
		justify-content: flex-start;
		text-align: left;
		width: 45vw;
	}
	.jobtitle {
		font-family: Montserrat;
		font-size: 16px;
		background-color: darkslategrey;
		padding: 4px 10px;
		color: whitesmoke;
		border-radius: 10px 10px 0 0;
	}
	@media screen and (max-width: 720px) {
		.panel-content {
			font-size: 16px;
		}
		.list {
			width: 100%;
			padding: 0;
		}
		.positiontitle {
			font-weight: 400;
			padding: 4px;
		}
		.skills {
			grid-template-columns: 1fr 1fr;
			line-height: 1.1;
		}
		.skill {
			font-size: 16px;
		}
	}
</style>
<div id="app">
	<div class="page-header">
		<div class="name">Srikant Gudi</div>
		<div>
			Bengaluru, India | 
			srikantgudi@gmail.com |
			+91 829 665 6336
		</div>
		<div class="positiontitle">Senior Front-end Engineer</div>
	</div>
	<div class="panel">
		<div class="panel-header">
			Profile
		</div>
		<div class="panel-content">
			<div class="panel-inner">
				<ul><li>Senior software professional with over 20 years of experience in various technologies</li><li>Currently into frontend development using Angular, Svelte, Stencil, React, NodeJS From April 2014</li><li>Working knowledge of Python-Django, MongoDB</li><li>Proficient in VueJS, creating web components using StencilJS, creating RESTful APIs based on MySQL, MongoDB</li><li>Proficient in creating POCs, prototypes, presentations, and wireframes</li><li>Can conduct trainings in the known technologies</li><li>Can mentor juniors and freshers</li><li>Interested in frontend architechture, providing solutions as independent developer</li></ul>
			</div>
		</div>
	</div>
	<div class="panel">
		<div class="panel-header">
			Technical Skills
		</div>
		<div class="panel-content">
			<div class="skills"><div class="skill">Angular</div><div class="skill">Svelte</div><div class="skill">VueJS</div><div class="skill">React</div><div class="skill">Stencil</div><div class="skill">JavaScript</div><div class="skill">TypeScript</div><div class="skill">HTML5</div><div class="skill">CSS3</div><div class="skill">SVG</div><div class="skill">Bootstrap</div><div class="skill">Angular-Material</div><div class="skill">React-UI</div><div class="skill">Vuetify</div><div class="skill">Buefy</div><div class="skill">Scrum</div><div class="skill">Sprint</div><div class="skill">JIRA</div><div class="skill">GIT</div><div class="skill">Confluence</div><div class="skill">VS Code</div><div class="skill">IntelliJ</div><div class="skill">Nodepad++</div><div class="skill">Windows</div><div class="skill">MacOS</div><div class="skill">Linux</div><div class="skill">Python-Django</div><div class="skill">Casandra</div></div>
		</div>
	</div>
	<div class="panel">
		<div class="panel-header">
			Work History
		</div>
		<div class="panel-content">
			<div class="panel-inner list">
				{#each data.exp as item}
					<div class="exp box">
						<div class="jobtitle">
							{item.jobTitle} :: {item.dates} &raquo;
						</div>
						<div class="expdetail">
							<div>
								{item.org}
							</div>
							<div>
								Technologies used: {item.technology}
							</div>	
							<div class="details">
								<details>
									<summary>Details</summary>
									<ul>
										{#each item.content as text}
										<li>{text}</li>
										{/each}
									</ul>
								</details>
							</div>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</div>	
</div>


