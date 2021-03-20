<script>
	import { data } from './data/data.js'
</script>

<style>
	.container {
		width: 90vw;
		height: 96vh;
		margin: 0 auto;
		overflow: hidden;
	}
	.pageheader {
		background: linear-gradient(lightblue,blue);
		border-radius: 1.5vw 1.5vw 0 0;
		margin-bottom: 8px;
	}
	.pagetitle {
		display: flex;
		padding: 10px;
		flex-flow: row;
		justify-content: center;
		color: whitesmoke;
		font-size: 3vw;
		font-family:  Righteous;
		text-transform: uppercase;
		font-weight:600;
	}
	.info {
		position: absolute;
		z-index: 999;
		top: 1vh;
		left: 5vw;
		width: 2vw;
		height: 2vh;
		display: flex;
		overflow: hidden;
		flex-flow: column;
		align-items: center;
		padding: 10px;
		box-shadow: 0 0 4px #fff;
		background: linear-gradient(lightblue,lightblue);
		transition: all 0.5s;
		border-radius: 40%;
	}
	.info:hover {
		width: fit-content;
		height: fit-content;
		line-height: 1.5;
		top: 2vh;
		left: 6vw;
		cursor: pointer;
	}
	.infobtn {
		display: block;
		cursor: pointer;
	}
	.info:hover {
		border-radius: 10%;
	}
	.info:hover > .infobtn {
		display: none;
	}
	.infotext {
		display: none;
		font-size: 1.2vw;
	}
	.info:hover > .infotext {
		display: block;
		width: fit-content;
		height: fit-content;
	}
	.positiontitle {
		font-family: 'Comic Sans MS';
		font-size: 1.5vw;
		display: flex;
		width: 70%;
		margin: 0 auto;
		margin-bottom: 10px;
		justify-content: space-around;
		background: linear-gradient(#6b705c,#ffe8d6,#6b705c);
	}
	.content {
		padding: 10px;
		display: flex;
		flex-flow: column;
		height: 90%;
	}
	.panel {
		box-shadow: 0 0 8px #666666;
		border-radius: 30%;
		width: 50%;
		height: 20%;
		margin: 0 auto;
		padding: 1%;
		display: flex;
		flex-flow: column;
		align-items: center;
		justify-content: space-around;
		transition: all 1s;
	}
	.panel-header {
		box-shadow: 0 0 4px #999;
		padding: 4px;
		width: 70%;
		text-align: center;
		transition: all 1s;
		border-radius: 10px;
		background-color: #eeeeee;
		font-size: 2vw;
	}
	.panel:hover {
		border-radius: 10px 10px 0 0;
		width: 70%;
		height: 50%;
		box-shadow: 0 4px 12px #009;
		background: linear-gradient(#0096c7,#caf0f8,#0096c7);
	}
	.panel-content {
		width: 60%;
		opacity: 0.3;
		height: 4vh;
		overflow: hidden;
		transition: all 1s;
	}
	.panel:hover > .panel-header {
		width: 90%;
		font-size: 1.5vw;
		margin: 0 auto;
		background: linear-gradient(#457b9d,#a8dadc,#457b9d);
		border-radius: 10px 10px 4px 4px;
		padding: 2%;
	}
	.panel:hover > .panel-content {
		width: 80%;
		height: 30vh;
		overflow-y: auto;
		opacity: 1;
		font-size: 100%;
	}
	.skills {
		display: grid;
		grid-template-columns: 1fr 1fr 1fr;
		padding: 10px;
	}
	.skill {
		transition: all 1s;
		width: auto;
		box-shadow: 0 0 4px #999;
		text-align: center;
		padding: 4px;
		margin: 0 4px 4px 0;
		font-family: Helvetica;
		font-size: 1vw;
		border-radius: 4px;
	}
	@media screen and (min-width: 721px) {
		.skills {
			grid-template-columns: 1fr 1fr;
		}
		.skill {
			font-size: 1.5vw;
		}
		.panel-content {
			font-size: 3vw;
		}
	}
	@media screen and (max-width: 720px) {
		.skills {
			grid-template-columns: 1fr 1fr;
		}
		.skill {
			font-size: 2vw;
		}
		.panel-content {
			font-size: 2vw;
		}
	}
	@media screen and (max-width: 420px) {
		.skills {
			grid-template-columns: 1fr;
		}
		.skill {
			font-size: 1vw;
		}
	}
</style>

<div class="container">
	<div class="pageheader">
		<div class="pagetitle">Srikant Gudi</div>
		<div class="info">
			<div class="infobtn">
				??
			</div>
			<div class="infotext">
				<div>
					srikantgudi@gmail.com
				</div>
				<div>
					+91 829 665 6336
				</div>
			</div>
		</div>
	</div>
	<div class="positiontitle">
		SENIOR FRONTEND PROFESSIONAL
	</div>
	<div class="content">
		<div class="panel">
			<div class="panel-header">
				PROFILE
			</div>
			<div class="panel-content">
				<ul><li>Senior software professional with over 20 years of experience in various technologies</li><li>Currently into frontend development using Angular, Svelte, Stencil, React, NodeJS From April 2014</li><li>Working knowledge of Python-Django, MongoDB</li><li>Proficient in VueJS, creating web components using StencilJS, creating RESTful APIs based on MySQL, MongoDB</li><li>Proficient in creating POCs, prototypes, presentations, and wireframes</li><li>Can conduct trainings in the known technologies</li><li>Can mentor juniors and freshers</li><li>Interested in frontend architechture, providing solutions as independent developer</li></ul>
			</div>
		</div>
		<div class="panel">
			<div class="panel-header">
				TECHNICAL SKILLS
			</div>
			<div class="panel-content">
				<div class="skills">
					{#each data.skills as skill}
					<div class="skill">{skill}</div>
					{/each}
				</div>
			</div>
		</div>
		<div class="panel">
			<div class="panel-header">
				WORK HISTORY
			</div>
			<div class="panel-content">
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