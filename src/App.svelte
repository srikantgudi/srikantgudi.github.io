<script>
	import { data } from './data/data';
	import SkillLevel from './SkillLevel.svelte';
</script>

<div class="page box">
	<div class="title">
		SRIKANT GUDI
	</div>
	<div class="position-title">
		SENIOR FRONTEND PROFESSIONAL
	</div>
	<div class="contact-details">
		<div class="contact-item">
			srikantgudi@gmail.com
		</div>
		<div class="contact-item">
			+91 829 665 6336
		</div>
		<div class="contact-item">
			<a href="https://www.linkedin.com/in/srikantgudi-blr/" target="_blank">LinededIN profile</a>
		</div>
		<div class="contact-item">
			SKYPE: srikantgudi
		</div>
		<div class="section-title">
			PROFILE
		</div>
		<div class="profile-details">
			{#each data.profile as text}
			<div class="profile-item">
				{text}
			</div>
			{/each}
		</div>
		<div class="section-title">
			TECHNICAL SKILLS
		</div>
		<div class="skills">
			{#each Object.keys(data.skills) as skill}
			<div class="skill">
				<SkillLevel ht={30} text={skill} level={data.skills[skill]} />
			</div>
			{/each}
		</div>
		<div class="section-title">
			WORK EXPERIENCE
		</div>
		<div class="exp">
			{#each data.exp as exp,expidx}
			<div class="exp-item">
				<div class="job-title">
					{exp.dates} :: {exp.jobTitle}
				</div>
				<div>
					{exp.org}
				</div>
				<div>
					Technologies used: {exp.technology}
				</div>
			</div>
			{/each}
		</div>
	</div>
</div>