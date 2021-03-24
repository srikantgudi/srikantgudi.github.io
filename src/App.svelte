<script>
	import Dialog from './Dialog.svelte';
	import WorkHistory from './WorkHistory.svelte';
	import SkillLevel from './SkillLevel.svelte'
	import { data } from './data/data';

	let name = 'world';
	let showDetailExp = false;
	let showDetailSkills = false;

	const detailSkills = () => {
		showDetailSkills = true;
	}
	const detailWorkExp = () => {
		showDetailExp = true;
	}
</script>

<style>
	.page {
		box-shadow: 0 2px 4px #999999;
		margin: 0 10%;		
		background: linear-gradient(to bottom,beige 90%, olive);
	}
	.topnav {
		height: 8vh;
		padding: 10px;
		display: flex;
		flex-flow: column;
		align-items: center;
		justify-content: space-around;
	}
	.content {
		display: flex;
		flex-flow: column;
	}
	.title {
		font-family: Roboto;
		font-weight: 600;
		font-size: 30px;
		text-transform: uppercase;
		color: navy;
	}
	.position-title {
		font-family: Orbitron;
		letter-spacing: 1px;;
		font-size: 20px;
	}
	.panel {
		font-family: Montserrat;
		display: flex;
		flex-flow: column;
		margin: 10px 10px 0;
		padding: 1%;
		font-size: 14px;
		box-shadow: 0 2px 2px #666666;
		background: linear-gradient(to bottom, #eeeeee 70%, #ddd);
	}
	.profile {
		width: 40vw;
	}
	.contact {
		width: 20vw;
	}
	.contact-details {
		box-sizing: border-box;
		padding: 0 20px;
		font-size: 16px;
		margin-top: 10px;
		line-height: 1.2;
	}
	.profile-details {
		font-size: 14px;
	}
	.sectiontitle {
		display: flex;
		font-family: Roboto;
		font-size: 18px;
		text-transform: uppercase;
		border-radius: 10px 10px 0 0;
		padding: 4px 10px;
		margin-bottom: 4px;
		background: linear-gradient(to right,darkblue 50%,lightblue);
		color: #ffffff;
	}
	.skills {
		
	}
	.exp {
		padding: 10px;
		margin: 10px;
	}
	
	:global(.icon-btn) {
		border: none;
		box-shadow: 0 2px 0 #999999;
		display: flex;
		align-items: center;
		justify-content: space-around;
		border-radius: 50%;
		width: 24px;
		height: 24px;
		margin: 0 10px;
		cursor: pointer;
		background-color: lightgrey;
		color: #333333;
	}
	@media screen and (max-width: 960px) {
		.page {
			padding: 20px 0;
			height: auto;
			margin: 0;
		}
		.title {
			font-size: 20px;
		}
		.position-title {
			font-size: 14px;
		}
		.contact-details {
			font-size: 10px;
		}
		.topnav {
			align-items: flex-start;
			padding: 0 10px;
		}
		.content {
			display: flex;
			flex-flow: column;
		}
		.panel {
			width: auto;
			height: auto;
			transition: all 1s eas-in-out;
		}
		.contact-details, .profile-details {
			font-size: 14px;
			line-height: 1.2;
			padding: 0 10px 10px
		}
		.skills {
			width: auto;
		}
	}
</style>
<div class="page">
	<div class="topnav">
		<div class="title">
			Srikant Gudi
		</div>
		<div class="position-title">
			Senior Frontend Professional
		</div>
	</div>
	<div class="content">
		<div class="panel">
			<div class="sectiontitle">
				Profile
			</div>
			<div class="profile-details">
				<ul>
					<li>20+ years total experience</li>
					<li>Since April 2014 into Frontend development using latest frameworks.</li>
					<li>Proficient in Angular, Svelte, React, VueJS, Stencil, NodeJS, MySQL</li>
					<li>Can create prototypes, presentations, wireframes</li>
					<li>Interested in newer frontend technologies</li>
					<li>Interested in frontend architecture and providing solutions as independent developer</li>
				</ul>
			</div>
		</div>
		<div class="panel">
			<div class="sectiontitle">
				Contact Details
			</div>
			<div class="contact-details">
				<div>
					srikantgudi@gmail.com
				</div>
				<div>
					+91 829 665 6336
				</div>
				<div>
					<a href="https://www.linkedin.com/in/srikantgudi-blr/">LinkedIN profile</a>
				</div>
				<div>
					Skype: srikantgudi
				</div>
			</div>
		</div>
		<div class="panel">
			<div class="sectiontitle">
				Technical Skills
			</div>
			<div>
				{#each Object.keys(data.skills) as skill}
				<SkillLevel width={390} ht={30} text={skill} level={data.skills[skill]} />
				{/each}
			</div>
		</div>
		<div class="panel exp">
			<div class="sectiontitle">
				Work Experience
			</div>
			<div>
				{#each data.exp as exp}
				<div class="panel">
					<div class="job-title">{exp.dates} :: {exp.jobTitle}</div>
					<div class="org-name">{exp.org}</div>
					<div class="org-name">{exp.technology}</div>
				</div>
				{/each}
			</div>
		</div>
	</div>
</div>