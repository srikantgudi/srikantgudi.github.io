<script>
	import { data } from './data/data.js'
	const winResize = e => {
		console.log('win-resize: e', e);
	}
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
		top: 1em;
		margin-left: 2em;
		display: flex;
		flex-flow: column;
		box-shadow: 0 2px 4px #999;
		padding: 10px;
		border-radius: 1em 1em 0 0;
		transition: all 0.5s;
		background: lightcyan;
		color: navy;
	}
	.infobtn {
		cursor: pointer;
		display: block;
	}
	.info-content {
		display: none;
	}
	.info:hover > .infobtn {
		display: none;
	}
	.info:hover > .info-content {
		display: flex;
		flex-flow: column;
		gap: 10px;
		transition: all 1s;
	}
	.grad-lite {
		background: linear-gradient(lightcyan,lightblue);
		color: navy;
	}
	.grad-dark {
		background: linear-gradient(grey, darkslategrey);
		color: whitesmoke!important;
	}
	.pagetitle {
		height: 3em;
		background: linear-gradient(lightblue,blue);
		color: whitesmoke;
		border-radius: 1em;
		text-align: center;
		padding: 10px;
	}
	.name {
		font-family: Righteous;
		font-size: 2vw;
		letter-spacing: 1px;
		text-transform: uppercase;
	}
	.positiontitle {
		font-size: 1.8vw;
		font-family: 'Comic Sans MS';
		font-weight: 600;
		padding: 10px;
		margin: 0 4vw;
		background: linear-gradient(lightblue,blue);
		color: lightcyan;
		border-radius: 1em;
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
		font-family: Verdana;
		color: navy;
		padding: 2vh 2vw;
		background-color: lightblue;
		border-radius: 20px 20px 0 0;
	}
	.profile {
		font-family: Montserrat;
		font-size: 1.2vw;
		line-height: 1.5;
		padding: 1em;
	}
	.contacts {
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.contact-item {
		min-width: 30%;
		text-align: center;
	}
	.box {
		box-shadow: 0 2px 20px #999999;
		border-radius: 0 0 10px 10px
	}
	.resume-content {
		opacity: 0.5;
		transition: all 1s;
	}
	.resume-content:hover {
		font-weight: 600;
		opacity: 1;
	}
	.list {
		padding: 10px 20px;
	}
	.edu {
		font-size: 12px;
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
		font-family: Montserrat;
		font-size: 16px;
		font-weight: 600;
		border-radius: 4px;
	}
	.exp {
		display: flex;
		flex-flow: column;
		padding: 10px;
	}
	.jobtitle {
		font-family: Montserrat;
		font-size: 1.5vw;
		background-color: darkslategrey;
		padding: 4px 10px;
		color: whitesmoke;
		border-radius: 10px 10px 0 0;
	}
	.expdetail {
		padding: 10px;
		text-align: center;
    	font-family: Montserrat;
		font-size: 1.2vw;
		opacity: 0.7;
		transition: all 0.5s;
	}
	.expdetail:hover {
		opacity: 1;
		font-weight: 600;
	}
	@media screen and (max-width: 720px) {
		.pagetitle {
			height: auto;
			padding: 10px;
		}
    .sectiontitle, .subsectiontitle {
      font-size: 90%;
    }
		.name {
			font-size: 80%;
		}
		.edu-list, .list {
			width: 100%;
			font-size: 12px;
			padding: 0;
		}
		.contacts {
			flex-flow: column;
			font-size: 70%;
		}
		.positiontitle {
			font-size: 8px;
			letter-spacing: 0;
		}
		.skills {
			grid-template-columns: 1fr;
			font-size: 90%;
			line-height: 1.1;
		}
	}
</style>
<div id="app" class="grad-app">
	<div class="topnav grad-lite">
		<div class="pagetitle">
			<div class="name">
				Srikant Gudi
			</div>
			<div class="edu-list">
				<span class="edu" title="Master in Computer Management">M.C.M.</span>
				<span class="edu" title="Bachelor of Commerce">B.Com.</span>
			</div>
		</div>
		<div class="info">
			<div class="infobtn">??</div>
			<div class="info-content">
				<div class="contact-item">
					Bengaluru, India
				</div>
				<div class="contact-item">
					srikantgudi@gmail.com
				</div>
				<div class="contact-item">
					+91 829 665 6336
				</div>
			</div>
		</div>
		<div class="positiontitle space-around">
			SENIOR FRONTEND ENGINEER
		</div>
	</div>
	<div>
		<div class="sectiontitle grad-dark space-around">
			&laquo; PROFILE &raquo;
		</div>
		<div class="box profile resume-content">
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
		<div class="box list resume-content">
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
		<div class="box list resume-content">
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
					</div>
				</div>
			{/each}
		</div>
	</div>
</div>