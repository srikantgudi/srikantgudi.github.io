<script>
	import { data } from './data/data.js'
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
	}
	.info {
		display: flex;
		flex-flow: column;
		box-shadow: 0 2px 4px #999;
		padding: 10px;
		border-radius: 1em 1em 0 0;
	}
	.grad-lite {
		background: linear-gradient(lightcyan,lightblue);
		color: navy;
	}
	.grad-dark {
		background: linear-gradient(grey, darkslategrey);
		color: whitesmoke;
	}
	.round-border-top {
		border-radius: 10px 10px 0 0;
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
    letter-spacing: 1px;
		font-weight: 600;
		text-transform: uppercase;
		font-size: 24px;
	}
	.positiontitle {
		font-size: 18px;
		font-family: Orbitron;
		font-weight: 600;
		padding: 10px;
		margin: 0 4vw;
		background: linear-gradient(lightblue,blue);
		color: whitesmoke;
		border-radius: 1em;
	}
	.space-around {
		display: flex;
		justify-content: space-around;
		align-items: center;
	}
	.sectiontitle {
		margin-top: 10px;
		box-sizing: border-box;
		font-size: 18px;
		font-family: Montserrat;
		font-weight: 600;
		color: navy;
		padding: 10px;
		background-color: lightblue;
		border-radius: 20px 20px 0 0;
	}
  .profile {
    font-family: Roboto;
    font-size: 14px;
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
	.list {
		padding: 10px 20px;
	}
	.edu {
		font-size: 12px;
	}
	.skills {
		display: flex;
		flex-flow: row wrap;
		font-family: Roboto;
		font-size: 14px;
	}
	.skill {
		min-width: 100px;
		box-shadow: 0 0 4px #999;
	}
	.exp {
		display: flex;
		flex-flow: column;
		padding: 10px;
	}
  .jobtitle {
    font-family: Montserrat;
    background-color: darkslategrey;
    padding: 4px 10px;
    color: whitesmoke;
    border-radius: 10px 10px 0 0;
  }
	.expdetail {
		padding: 10px;
		text-align: center;
    font-family: Roboto;
	}
	@media screen and (max-width: 840px) {
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
	}
</style>
<div id="app" class="grad-app">
	<div class="info grad-lite">
		<div class="pagetitle">
			<div class="name">
				Srikant Gudi
			</div>
			<div class="edu-list">
				<span class="edu" title="Master in Computer Management">M.C.M.</span>
				<span class="edu" title="Bachelor of Commerce">B.Com.</span>
			</div>
		</div>
		<div>
			
		</div>
		<div class="contacts">
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
		<div class="positiontitle space-around">
			SENIOR FRONTEND ENGINEER
		</div>
	</div>
	<div>
		<div class="sectiontitle grad-lite">
			PROFILE
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
		<div class="sectiontitle grad-lite">
			TECHNICAL SKILLS
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
		<div class="sectiontitle grad-lite">
			WORK EXPERIENCE
		</div>
		<div class="box list">
			{#each data.exp as item}
				<div class="exp box">
					<div class="jobtitle">
						{item.jobTitle} - {item.dates}
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