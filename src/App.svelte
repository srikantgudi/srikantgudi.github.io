<script>
	import { data } from './data/data.js'
	const winResize = e => {
		console.log('win-resize: e', e);
	}
	let showInfo = false;
</script>
<style>
	#app {
		width: 60vw;
		height: auto;
		margin: 0 auto;
		padding: 10px;
		background: linear-gradient(lightblue,lightcyan,lightblue);
		color: navy;
		line-height: 1.2;
		font-family: Montserrat;
	}
	.info {
		position: absolute;
		top: 2em;
		display: flex;
		flex-flow: column;
		align-items: center;
		box-shadow: 0 2px 4px #023e8a;
		padding: 4px;
		border-radius: 50%;
		transition: all 0.5s;
		background: linear-gradient(#90e0ef,#caf0f8,#90e0ef);
		color: navy;
	}
	.info.active {
		box-shadow: 0 2px 14px #457b9d;
		border-radius: 10%;
	}
	.infobtn {
		cursor: pointer;
		display: flex;
		align-items: center;
		justify-content: space-around;
		width: 1em;
		border-radius: 50%;
	}
	.infobtn.hide {
		display: none;
	}
	.infoclose {
		cursor: pointer;
		border: none;
		border-radius: 50%;
		background-color: lightgrey;
	}
	.info-content {
		display: none;
	}
	.info-content.active {
		display: flex;
		flex-flow: column;
		gap: 10px;
		transition: all 1s;
		height: 15vh;
	}
	.grad-lite {
		background: linear-gradient(lightcyan,lightblue);
		color: navy;
	}
	.grad-dark {
		background: linear-gradient(grey, darkslategrey);
		color: whitesmoke!important;
	}
	.profile {
		font-family: 'Helvetica Neue';
	}
	.pagetitle {
		height: 3em;
		background: linear-gradient(#023e8a,#caf0f8,#023e8a);
		color: whitesmoke;
		border-radius: 1em;
		text-align: center;
		padding: 10px;
	}
	.name {
		font-family: Righteous;
		font-weight: 600;
		font-size: 3vw;
		letter-spacing: 1px;
		text-transform: uppercase;
		color: #1d3557;
	}
	@keyframes animPositionTitle {
		from {color: beige;}
		to {color: #03045e;}
	}
	.positiontitle {
		font-size: 2vw;
		font-family: Ubuntu;
		font-weight: 600;
		padding: 1vw 1vh;
		margin: 1vh 4vw;
		background: linear-gradient(#343a40,#dee2e6,#343a40);
		color: #6d6875;
		border-radius: 1em;
		animation: animPositionTitle 5s ease-in-out infinite reverse;
	}
	.space-around {
		display: flex;
		justify-content: space-around;
		align-items: center;
	}
	.sectiontitle {
		display: flex;
		flex-flow: column;
		margin-top: 10px;
		font-size: 1.8vw;
		font-family: Orbitron;
		letter-spacing: 2px;
		color: navy;
		padding: 2vh 2vw;
		background-color: lightblue;
		border-radius: 20px 20px 0 0;
	}
	.profile {
		font-family: Ubuntu;
		line-height: 1.5;
		padding: 1em;
		transition: all 1s;
	}
	.profile:hover {
		font-weight: 600;
	}
	.contact-item {
		min-width: 30%;
		text-align: center;
	}
	.box {
		box-shadow: 0 2px 20px #999999;
		border-radius: 0 0 10px 10px
	}
	.list {
		padding: 10px 20px;
	}
	.edu {
		font-size: 12px;
	}
	.edu:nth-child(n+1):before {
		content: '\bb\20';
	}
	.skills {
		display: grid;
		grid-template-columns: 1fr 1fr 1fr 1fr;
		font-family: Roboto;
		font-size: 14px;
		padding: 10px;
	}
	.skill {
		transition: all 1s;
		min-width: 22%;
		box-shadow: 0 0 4px #999;
		text-align: center;
		padding: 4px;
		margin: 0 4px 4px 0;
		font-family: Ubuntu;
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
		margin-left: 10vw;
    	font-family: Ubuntu;
	}
	.expdetail > .details {
		display: flex;
		justify-content: flex-start;
		text-align: left;
		width: 40vw;
	}
	.jobtitle {
		font-family: Montserrat;
		font-size: 1.5vw;
		background-color: darkslategrey;
		padding: 4px 10px;
		color: whitesmoke;
		border-radius: 10px 10px 0 0;
	}
	@media screen and (max-width: 720px) {
		.info {
			top: 5vh;
			margin-left: 1em;
			padding: 2px 0 4px;
			font-size: 12px;
			height: auto;
		}
		.pagetitle {
			height: auto;
			padding: 10px;
		}
		.sectiontitle {
			font-size: 80%;
		}
		.edu-list, .list {
			width: 100%;
			font-size: 8px;
			font-family: sans-serif;
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
		.skill, .edu {
			font-size: 10px;
		}
	}
</style>
<div id="app" class="grad-app">
	<div class="topnav grad-lite">
		<div class="pagetitle">
			<div class="name">
				Srikant Gudi
			</div>
			<div class="info" class:active={showInfo} on:click={() => {showInfo = true}}>
				<div class="infobtn" class:hide={showInfo} >&quest;</div>
				<div class="info-content" class:active={showInfo}>
					<div class="contact-item">
						Bengaluru, India 
						<button class="infoclose" on:click|stopPropagation={() => {showInfo=false}}>&times;</button>
					</div>
					<div class="contact-item">
						srikantgudi@gmail.com
					</div>
					<div class="contact-item">
						+91 829 665 6336
					</div>
					<div class="edu-list">
						<div class="edu">Master in Computer Management</div>
						<div class="edu">Bachelor of Commerce</div>
					</div>
				</div>
			</div>
		</div>
		
		<div class="positiontitle space-around">
			Senior Front-end Engineer
		</div>
	</div>
	<div>
		<div class="sectiontitle grad-dark space-around">
			&laquo; PROFILE &raquo;
		</div>
		<div class="box profile">
			<ul>
				{#each data.profile as text}
				<li>{text}</li>
				{/each}
			</ul>
		</div>
	</div>
	<div>
		<div class="sectiontitle grad-dark space-around">
			&laquo; TECHNICAL SKILLS &raquo;
		</div>
		<div class="box list">
			<div class="skills">
				{#each data.skills as text}
				<div class="skill">{text}</div>
				{/each}
			</div>
		</div>
	</div>
	
	<div>
		<div class="sectiontitle grad-dark space-around">
			&laquo; WORK EXPERIENCE &raquo;
		</div>
		<div class="box list">
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