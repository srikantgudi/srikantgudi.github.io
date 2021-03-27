<script>
	import Rating from './Rating.svelte';
	let name = 'world';
	let skills = [
		{name: 'Angular', rating: 8},
		{name: 'Svelte', rating: 8},
		{name: 'Vuejs', rating: 7},
		{name: 'React', rating: 7},
		{name: 'JavaScript', rating: 8},
		{name: 'TypeScript', rating: 8},
		{name: 'HTML5', rating: 8},
		{name: 'CSS3', rating: 8},
		{name: 'NodeJS', rating: 7},
	];
	let exp = [
		{
			dates: 'June 2016 to present',
			jobtitle: 'Project lead',
			org: 'Mphasis',
			details: [
			''
		]
		},
		{
			dates: 'June 2015 to Jan 2016',
			jobtitle: 'Senior AngularJS developer',
			org: 'Pandera Solutions'
		},
		{
			dates: 'Aug 2014 to Jan 2015',
			jobtitle: 'Senior UI Developer',
			org: 'Basil Communications'
		},
		{
			dates: 'Apr 2014 to Jun 2014',
			jobtitle: 'Senior AngularJS Developer',
			org: 'Satsyl, VA, USA'
		},
		{
			dates: 'Nov 2011 to March 2014',
			jobtitle: 'Senior Software Developer',
			org: 'MModal Global Services (client of SUNSYSTEMS)'
		},
		{
			dates: 'Feb 2010 to Sep 2011',
			jobtitle: 'Senior Software Engineer',
			org: 'TechJini Solutions'
		},
		{
			dates: 'July 2007 to March 2009',
			jobtitle: 'Senior Software Engineer',
			org: 'TLI Software'
		},
		{
			dates: 'Jan 2007 to July 2007',
			jobtitle: 'Software Engineer',
			org: 'Vital Data Systems, Hyderabad'
		},
		{
			dates: 'July 2006 to Dec 2006',
			jobtitle: 'Project Manager',
			org: 'Harini Software Solutions, Chennai'
		},
		{
			dates: 'Nov 2005 to June 2006',
			jobtitle: 'Senior Programmer',
			org: 'Ezynes Communications, Chennai'
		},

	];
	</script>

<style>
	#app {
		display: flex;
		flex-flow: column;
		width: 90vw;
		margin: 0 auto;
		min-height: 90vh;
		background: linear-gradient(#a5a58d,#a5a58d, #a5a58d) repeat-y 50% 30%;
	}
	.topnav {
		background: linear-gradient(#023e8a,#90e0ef);
		padding: 0 3em;
		margin: 2em;
	}
	
	.apptitle {
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 4em;
		padding: 0;
		margin: 0;
		color: #0077b6;
		font-weight: 600;
		font-family: Montserrat;
		text-shadow: 1px -4px 4px #ade8f4;
	}
	.position-title {
		display: flex;
		align-items: center;
		justify-content: space-around;
		color: #90e0ef;
		font-size: 3vw;
		font-family: cursive;
		display: flex;
	}
	.speciality {
		display: flex;
		align-items: center;
		justify-content: space-around;
		color: #caf0f8;
		font-family: Montserrat;
		font-size: 1.2em;
		margin: 0 auto;
		padding: 4px;
	}
	.contact {
		width: 40vw;
		margin: 1em auto;
		display: flex;
		flex-flow: row wrap;
		justify-content: space-around;
		text-align: center;
	}
	.contact-item {
		min-width: 10em;
		margin: 10px;
		color: #03045e;
	}
	.content {
		width: 60vw;
		margin: 10px auto;
		padding: 10px 20px;
		box-shadow: 0 0 4px #999;
		transition: all 1s;
		box-shadow: 0 2px 12px #009;
		background: linear-gradient(#bde0fe,#a2d2ff);
	}
	.content:hover {
		width: 80%;
		font-weight: 600;
		border-radius: 20px 20px 10px 10px;
	}
	.content:hover > .section-title {
		border-radius: 10px 10px 40% 40%;
	}
	.content:hover > .content-details {
		border-radius: 20% 20% 0 0;
	}
	.content-details {
		padding: 20px;
		box-shadow: 0 2px 10px;
		transition: all 1s;
		background-color: #f0efeb;
	}
	.profile-item {
		text-indent: -14px;
		margin-left: 18px;
		font-size: 1.2vw;
		transition: all 1s;
	}
	.profile-item:before {
		content: '\bb\20';
	}
	.linkedin {
		text-decoration: none;
		padding-bottom: 1px;
		border-bottom: 1px solid #ffffff;
		color: #03045e;
	}
	.section-title {
		text-align: center;
		font-size: 2em;
		font-weight: 600;
		font-family: Orbitron;
		background: linear-gradient(#457b9d,#a8dadc,#457b9d);
		padding: 1% 0;
		color: navy;
		transition: all 1s;
	}
	.skills, .exp-list {
		display: flex;
		flex-flow: row wrap;
		justify-content: space-around;
	}
	.skill, .exp {
		width: 15em;
		box-shadow: 0 2px 10px;
		padding: 10px;
		margin: 10px;
		border-radius: 10px;
	}
	.exp {
		font-family: Ubuntu;
	}
	.exp-dates {
		background-color: lightblue;
		padding: 10px;
		font-weight: 600;
	}
	.exp-jobtitle {
		background-color: lightgrey;
		padding: 10px;
	}
	.exp-org {
		background-color: #def;
		padding: 10px;
	}
	@media screen and (max-width: 640px) {
		#app {
			margin: 0;
			padding: 0;
		}
		.topnav {
			margin: 0;
		}
		.apptitle {
			font-size: 1.5em;
			margin-top: 10px;
		}
		.position-title {
			font-size: 1.2em;
			display: flex;
			justify-content: space-around;
		}
		.speciality {
			background: transparent;
			display: flex;
			font-size: 1em;
			margin: 0 10%;
			justify-content: space-around;
		}
		.contact, .linkedin {
			color: #023e8a;
		}
		.contact-item {
			margin: 0 auto;
		}
		.section-title {
			font-size: 1.5em;
		}
	}
</style>

<main id="app">
	<div class="topnav">
		<div class="apptitle">
			SRIKANT GUDI
		</div>
		<div class="position-title">
			Senior FrontEnd Professional
		</div>
		<div class="speciality">
			<small>
				Specialized in:
				<ul>
					<li>
						Frontend development using Angular, Svelte, VueJS, React
					</li>
					<li>
						Web components development using Stencil and Vanilla JavaScript	
					</li>
					<li>
						API development using NodeJS
					</li>
				</ul>
			</small>
		</div>
		<div class="contact">
			<div class="contact-item">
				Bengaluru, India
			</div>
			<div class="contact-item">
				srikantgudi@gmail.com
			</div>
			<div class="contact-item">
				+91 829 665 6336
			</div>
			<div class="contact-item">
				<a class="linkedin" target="_blank" href="https://www.linkedin.com/in/srikantgudi-blr/">
					LinkedIn Profile
				</a>
			</div>
			<div class="contact-item">
				SKYPE: srikantgudi
			</div>
		</div>
	</div>
	
	<div class="content">
		<div class="section-title">
			PROFILE
		</div>
		<div class="content-details">
			<div class="profile-item">Senior software professional with over 20 years of experience in various technologies </div><div class="profile-item">Currently into frontend development using Angular, Svelte, Stencil, React, NodeJS From April 2014 </div><div class="profile-item">Working knowledge of Python-Django, MongoDB. Proficient in VueJS, creating web components using StencilJS, creating RESTful APIs based on MySQL, MongoDB. Proficient in creating POCs, prototypes, presentations, and wireframes </div><div class="profile-item">Can conduct trainings in the known technologies. Can mentor juniors and freshers </div><div class="profile-item">Interested in frontend architechture, providing solutions as independent developer </div>
		</div>
	</div>
	
	<div class="content">
		<div class="section-title">
			SKILLS
		</div>
		<div class="content-details">
			<div class="skills">
				{#each skills as skill}
				<div class="skill">
					<Rating text={skill.name} rating={skill.rating} />
				</div>
				{/each}
			</div>
		</div>
	</div>
	
	<div class="content">
		<div class="section-title">
			WORK HISTORY
		</div>
		<div class="content-details exp-list">
			{#each exp as xp}
			<div class="exp">
				<div class="exp-dates">{xp.dates}</div>
				<div class="exp-jobtitle">{xp.jobtitle}</div>
				<div class="exp-org">{xp.org}</div>
			</div>
			{/each}
		</div>
	</div>
</main>