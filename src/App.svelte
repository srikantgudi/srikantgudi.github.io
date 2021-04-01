<script>
	import Rating from './Rating.svelte';
  	import {data} from './data/data';
	let name = 'world';
	let winwid;
	let tab=0;
	const toggleTab = (ptab) => {
		tab = tab === ptab ? 0 : ptab;
	}
</script>
<svelte:window bind:innerWidth={winwid} />
<style>
	.resume {
		margin-bottom: 2em;
		font-family: Montserrat;
	}
	.topnav {
		position: absolute;
		box-sizing: border-box;
		padding: 4px;
		left: 30vw;
		right: 30vw;
		margin: 0 auto;
		font-size: 1vmin;
		text-align: center;
		background: linear-gradient(aliceblue,lightcyan);
		box-shadow: 0 0 10px #999999;
		border-radius: 10px;
	}
	.info {
		position: absolute;
		top: 5vh;
		left: 5vw;
		height: 11vh;
		display: flex;
		flex-flow: column;
		align-items: center;
		justify-content: space-around;
		background-color: #def;
		padding: 1vh 1vw;
		z-index: 999;
		transition: all 1s;
		opacity: 1;
		text-align: center;
		border-radius: 20px;
		transform: scale(0.7);
	}
	.info:hover, .info.active {
		transform: scale(1);
		z-index: 999;
	}
	.contact {
		font-size: 1vw;
		position: absolute;
		top: 4vh;
		font-size: 12px;
		right: 15vw;
		padding: 1vh 2vw;
		transform: scale(0.5);
		opacity: 0.5;
		transition: all 1s;
		text-align: center;
		line-height: 1.5;
	}
	.contact:hover, .contact.active {
		font-size: 14px;
		z-index: 999;
		background-color: whitesmoke;
		transform: scale(1);
		opacity: 1;
	}
	.title {
		font-size: 3vw;
		font-family: Georgia;
		font-weight: 600;
		color: navy;
	}
	.positiontitle {
		font-size: 2vw;
		font-family: Orbitron;
		letter-spacing: 1px;
	}
	.title,	.positiontitle {
		left: 5vw;
		right: 5vw;
		display: flex;
		justify-content: space-around;
	}
	.profile {
		position: absolute;
		right: 5vw;
		top: 15vh;
		left: 10vw;
		width: 40vw;
		height: 50vh;
		overflow-y: hidden;
		background-color: whitesmoke;
		transform: scale(0.7);
		transition: all 1s;
		opacity: 0.4;
	}
	.profile:hover, .profile.active {
		z-index: 999;
		overflow-y: auto;
		transform: scale(1);
		opacity: 1;
		background-color: whitesmoke;
	}
	.skills {
		display: block;
		position: absolute;
		top: 15vh;
		right: 10vw;
		width: 40vw;
		height: 30vh;
		padding: 10px;
		overflow-y: hidden;
		background-color: whitesmoke;
		transform: scale(0.7);
		transition: all 1s;
	}
	.skills:hover, .skills.active {
		overflow-y: auto;
		z-index: 999;
		height: 65vh;
		width: 60vw;
		transform: scale(1);
	}
	.skill {
		display: grid;
		grid-template-columns: 1fr 1fr;
		margin-top: 10px;
		align-items: center;
		gap: 10px;
	}
	.skills-list {
		margin-left: 2vw;
		display: grid;
		grid-template-columns: repeat(5,1fr);
	}
	.works {
		position: absolute;
		top: 40vh;
		right: 5vw;
		height: 40vh;
		margin: 0 5vw;
		overflow-y: hidden;
		background-color: whitesmoke;
		transform: scale(0.7);
		opacity: 0.5;
		font-size: 12px;
		transition: all 1s;
	}
	.works:hover, .works.active {
		z-index: 999;
		height:60vh;
		transform: scale(1);
		opacity: 1;
		overflow-y: auto;
		font-size: 14px;
	}
	.panel {
		box-shadow: 0 0 2px #999;
		box-shadow: 0 2px 12px #666666;
	}
	.panel-header {
		z-index: 999;
		padding: 1vh 2vw;
		font-size: 2.5vw;
		background: linear-gradient(to right,lightcyan,grey);
		border-radius: 10% 10% 30% 4%;
		box-shadow: 0 4px 1px #999999;
		opacity: 1;
	}
	.panel-content {
		font-size: 1vw;
	}
	.exp {
		display: flex;
		flex-flow: row wrap;
		gap: 10px;
		padding: 1vh 2vw;
		justify-content: space-around;
	}
	.exp-item {
		display: flex;
		flex-flow: column;
		text-align: center;
		border-radius: 10px 10px 0 0;
		box-shadow: 0 2px 6px #999;
		width: 20em;
		padding: 10px;
	}
	.job-title {
		font-family: Orbitron;
		letter-spacing: 1px;
		text-align: center;
	}
</style>
<div class="resume">
	<div class="topnav">
		Click / tap on each section to see the animation effect!
	</div>
	<div class="info" class:active={tab===1} on:click={() => toggleTab(1)}>
		<div class="title">
			SRIKANT GUDI
		</div>
		<div class="positiontitle">
			Senior FrontEnd Professional
		</div>
	</div>
	<div class="panel contact" class:active={tab===2} on:click={() => toggleTab(2)}>
		<div class="panel-header">
			Contact details
		</div>
		<div>
			Bengaluru, India
		</div>
		<div>
			srikantgudi@gmail.com
		</div>
		<div>
			+91 829 665 6336
		</div>
		<div>
			LinkedIN Profile
		</div>
		<div>
			SKYPE: srikantgudi
		</div>
	</div>
	<div class="aboutme">
		<div class="panel profile"  class:active={tab===3} on:click={() => toggleTab(3)}>
			<div class="panel-header">
				PROFILE
			</div>
			<div class="panel-content">
				<ul>
					{#each data.profile as text}
						<li>{text}</li>
					{/each}
				</ul>
			</div>
		</div>
	</div>
	<div class="panel skills"  class:active={tab===4} on:click={() => toggleTab(4)}>
		<div class="panel-header">
			TECHNICAL SKILLS
		</div>
		<div class="panel-content skills-list">
			{#each data.skills.primary as pskill}
			<div class="skill">
				<Rating text={pskill.name} rating={pskill.rating} clr={pskill.clr} />
			</div>
			{/each}
		</div>
	</div>
	<div class="panel works"  class:active={tab===5} on:click={() => toggleTab(5)}>
		<div class="panel-header">
			WORK EXPERIENCE
		</div>
		<div class="panel-content">
			<div class="exp">
				{#each data.exp as xp}
				<div class="exp-item">
					<div>{xp.dates}</div>
					<div class="job-title">{xp.jobTitle}</div>
					<div>{xp.org}</div>
					<div>Technologies used: {xp.technology}</div>
				</div>
				{/each}
			</div>
		</div>
	</div>
</div>
