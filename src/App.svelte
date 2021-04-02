<script>
	import Rating from './Rating.svelte';
  	import {data} from './data/data';
	let name = 'world';
</script>

<style>
</style>

<div class="resume">
	<div class="topnav">
		<div class="title">
			SRIKANT GUDI
		</div>
		<div class="contacts">
			<div class="contact-item">
				srikantgudi@gmail.com
			</div>
			<div class="contact-item">
				+91 829 665 6336
			</div>
		</div>
		<div class="positiontitle">
			Senior FrontEnd Professional
		</div>
		<div class="contacts">
			<div class="contact-item">
				<a href="https://linkedin.com/in/srikantgudi-blr">LinkedIn Profile</a>
			</div>
			<div class="contact-item">
				SKYPE: srikantgudi
			</div>
		</div>
	</div>
	<div class="panel">
		<div class="panel-title">
			PROFILE
		</div>
		<div class="panel-content">
			{#each data.profile as text}
			<div class="content-item">
				{text}
			</div>
			{/each}
		</div>
	</div>
	<div class="panel">
		<div class="panel-title">
			TECHNICAL SKILLS
		</div>
		<div class="panel-content">
			<div class="skills">
				{#each data.skills.primary as skill}
					<div class="skill primary">
						<Rating text={skill.name} rating={skill.rating} clr={skill.clr} />
					</div>
				{/each}
			</div>
			<div class="skills">
				{#each data.skills.secondary as skill}
					<div class="skill secondary">
						{skill.name}
					</div>
				{/each}
			</div>
		</div>
	</div>
	<div class="panel">
		<div class="panel-title">
			WORK EXPERIENCE
		</div>
		<div class="work-exp">
			{#each data.exp as xp}
				<div class="exp">
					<div>
						{xp.dates}
					</div>
					<div>
						{xp.jobTitle}
					</div>
					<div>
						{xp.org}
					</div>
					<div>
						<small>Technologies used:</small>
					</div>
					<div>
						<small>{xp.technology}</small>
					</div>
				</div>
			{/each}
		</div>
	</div>
</div>