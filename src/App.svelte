<script>
	import { data } from './data/data.js'
	const winResize = e => {
		console.log('win-resize: e', e);
	}
	let showInfo = false;
	let curTab = 1;
</script>
<style>
	.container {
		margin: 0 20%;
		padding: 10px;
		height: 90vh;
		transition: all 1s ease-in;
		border-radius: 10px 10px 0 0;
		box-shadow: 0 4px 10px #666666;
		overflow: hidden;
	}
	.content {
		background: lightcyan;
		padding: 10px;
		overflow: hidden;
		width: 60vw;
		margin: 0 auto;
	}
	.content-body {
		height: 5vh;
		transition: all 1s;
		opacity: 0.3;
		padding: 10px;
		overflow: hidden;
		font-family: Montserrat;
	}
	.content-body.active {
		opacity: 1;
		height: 30vh;
		overflow-y: auto;
	}
	.sectiontitle {
		box-shadow: 0 0 4px #999999;
		background: darkslategrey;
		color: whitesmoke;
		font-size: 3vw;
		padding: 10px;
		display: flex;
		border-radius: 30px 30px 0 0;
		justify-content: space-around;
	}
	.pageheader {
		text-align: center;
		margin-bottom: 10px;
	}
	.name {
		font-size: 1vw;
	}
	.info {
		position: absolute;
		top: 2em;
		font-family: Montserrat;
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
	.name {
		font-family: Righteous;
		font-weight: 600;
		font-size: 3vw;
		letter-spacing: 1px;
		text-transform: uppercase;
		color: #014f86;
	}
	@keyframes animPositionTitle {
		0% {color: #03045e;font-size: 2vw;}
		/* 25% {color: #023e8a;font-size: 1.5vw;} */
		50% {color: #caf0f8;font-size: 1vw;}
		/* 75% {color: #023e8a;font-size: 1.5vw;} */
		100% {color: #03045e;font-size: 2vw;}
	}
	.positiontitle {
		display: flex;
		justify-content: space-around;
		letter-spacing: 1px;
		font-size: 1.5vw;
		font-family: 'Comic Sans MS';
		font-weight: 600;
		padding: 10px;
		margin: 1vh 4vw;
		background: linear-gradient(#b7b7a4,#fff1e6,#b7b7a4);
		color: #6d6875;
		border-radius: 1em;
		animation: animPositionTitle 5s ease-in-out infinite reverse;
	}
	.expdetail {
		padding: 10px;
		text-align: left;
		margin-left: 5vw;
    	font-family: Montserrat;
	}
	.expdetail > .details {
		display: flex;
		justify-content: flex-start;
		text-align: left;
		width: 45vw;
		margin: 0 auto;
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
	.box {
		box-shadow: 0 2px 20px #999999;
		border-radius: 0 0 10px 10px
	}
	.skills {
		display: grid;
		grid-template-columns: 1fr 1fr 1fr;
		font-family: Roboto;
		font-size: 14px;
		padding: 10px;
	}
	.skill {
		transition: all 1s;
		min-width: 22%;
		box-shadow: 0 2px 2px #999;
		text-align: center;
		margin: 0 4px 4px 0;
		font-family: Montserrat;
		font-size: 18px;
		border-radius: 4px;
	}
	.exp {
		display: flex;
		flex-flow: column;
		padding: 10px;
	}
	.expdetail > .details {
		display: flex;
		justify-content: flex-start;
		text-align: left;
		width: 45vw;
	}
	.jobtitle {
		font-family: Montserrat;
		font-size: 1.5vw;
		background-color: darkslategrey;
		padding: 4px 10px;
		color: whitesmoke;
		border-radius: 10px 10px 0 0;
	}
	@media screen and (max-width: 480px) {
		.skills {
			grid-template-columns: 1fr 1fr 1fr;
			line-height: 1.1;
		}
	}

	@media screen and (max-width: 720px) {
		.info {
			top: 5vh;
			margin-left: 1em;
			padding: 2px 0 4px;
			font-size: 12px;
			height: auto;
		}
		.pageheader {
			height: auto;
			font-size: vw;
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
		.profile {
			font-size: 2vw;
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

<div class="container">
	<div class="pageheader">
		<div class="name">SRIKANT GUDI</div>
	</div>
	<div class="positiontitle">
		Senior Frontend Professional
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
	<div class="sectiontitle" on:click={() => {curTab=1}}>
		Profile
	</div>
	<div class="content-body" class:active={curTab === 1}>
		<ul>
			{#each data.profile as text}
			<li>{text}</li>
			{/each}
		</ul>
	</div>
	<div class="sectiontitle" on:click={() => {curTab=2}}>
		Technical Skills
	</div>
	<div class="content-body" class:active={curTab === 2}>
		<div class="skills">
			{#each data.skills as text}
			<div class="skill">{text}</div>
			{/each}
		</div>
	</div>
	
	<div class="sectiontitle" on:click={() => {curTab=3}}>
		Work History
	</div>
	<div class="content-body" class:active={curTab === 3}>
		{#each data.exp as item}
			<div class="box">
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

