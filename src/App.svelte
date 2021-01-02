<script>
	import Stars from './Stars.svelte';

	let name = 'world';
	let resume = {
		'info': {
			'name': 'INFO',
			'pos': 'SENIOR FRONT-END ENGINEER',
			'loc': 'Bengaluru, India',
			'email': 'srikantgudi@gmail.com',
			'phone': '+91-829-655-6336'
		},
		'profile': {
			title: 'PROFILE',
			contents: [
				'Senior Software Professional with over 20+ years of experience in various technologies',
				'Into Front-end development since 2014',
				'Proficient in Svelte, Angular, React, VueJs, StencilJS, NodeJS, MySQL',
				'Having working knowledge of Python-Django, MongoDB',
				'Can create POCs, Presentations'
			]
		},
		'skills': {
			title: 'TECHNICAL SKILLS',
			groups: [
				{
					name: 'Frameworks', values: [
						{skill:'Svelte',rating: 8},
						{skill:'Angular',rating: 8},
						{skill:'React',rating: 7},
						{skill:'Vue',rating:7},
						{skill:'Stencil',rating:6},
						{skill:'NodeJS',rating:7}
					]
				},
				{
					name: 'Web Skills',
					values: [
						{skill:'HTML5',rating:8},
						{skill:'CSS3',rating:8},
						{skill:'JavaScript',rating:8},
						{skill:'SVG',rating:6}
					]
				},
				{
					name:'Databases',
					values: [
						{skill:'MongoDB',rating:7},
						{skill:'MySQL',rating:7}
					]
				},
				{
					name:'Version Control',
					values: [
						{skill:'Git',rating:7},
						{skill:'BitBucket',rating:7}
					]
				},
				{
					name: 'Others',
					values: [
						{skill:'Visual Studio Code',rating:8},
						{skill:'IntelliJ',rating:8},
						{skill:'Atom',rating:8},
						{skill:'MacOS',rating:8},
						{skill:'Linux',rating:8},
						{skill:'Windows',rating:8}
					]
				}
			]
		},
		'exp': {
			title: 'WORK EXPERIENCE',
			expList: [
				{
					header: {
						dates: '16-Jun-2016 to present',
						jobTitle: 'Project Lead - System',
						org: 'Mphasis, Bengaluru',
					},
					content: [
		        'Currently working as Lead frontend developer with Schneider Electric',
						'Worked offshore in Bengaluru with a banking conglomerate on  projects in Angular and React',
						'Worked onsite in Glasgow, UK with a banking conglomerate on Angular based projects',
						'Developed UI for a POC for Digital Readiness Analysis Tool to create a survey questionnaire for various categories using Angular, Material Design, HTML5, CSS3, JavaScript, API integration',
						'Developed UI for client in Insurance domain using React, Material-UI, HTML5, CSS3, JavaScript, IndexedDB',
						'Worked offshore at client-side with Schneider Electric on Management Dashboard using Angular 1.x',
					]
				},
				{
					header: {
						dates: '15-Aug-2015 to 14-Jan-2016',
						jobTitle: 'Senior AngularJS Developer',
						org: 'Pandera Solutions India Pvt Ltd, Bengaluru',
					},
					content: [
						'Worked in Angular on various projects',
						'Created sub-components for re-use',
						'Interacted with client-side developers to understand the requirements',
						'Integrated APIs in the frontend code'
					]
				},
				{
					header: {
						dates: '20-Aug-2014 to 22-Jan-2015',
						jobTitle: 'Senior Software Developer',
						org: 'Basil Communications Pvt Ltd, Bengaluru',
					},
					content: [
						'Created HTML mockups for various applications',
						'Interacted with designers to understand the designs',
						'Used Photoshop to slice images'
					]
				},
				{
					header: {
						dates: 'Apr-2014 to Jun-2014',
						jobTitle: 'Senior AngularJS Developer',
						org: 'Satsyil, VA, USA (Remote work)',
					},
					content: [
						'Worked remotely as senior UI developer using AngularJS technology',
						'Modified admin-side modules and screen layouts and created new ones as required'
					]
				},
				{
					header: {
						dates: '23-Nov-2011 – 07-Mar-2014',
						jobTitle: 'Senior Software Developer',
						org: 'Tejas Systems / SUNSYSTEMS, Bengaluru :: Client: MModal Global Services Pvt Ltd',
					},
					content: [
						'Environment: PHP, MySQL, Jquery, Fancybox, Fusioncharts, HTML, CSS (Bootstrap), AngularJS',
						'modified client-side and admin-side scripts',
						'created animated presentation of iPad application using Jquery and Jquery-cycle',
						'created presentation of mobile application in Powerpoint',
						'created UI for password management using AngularJS'
					]
				},
				{
					header: {
						dates: '12-Feb-2010 –22-Sep-2011',
						jobTitle: 'Senior Software Engineer',
						org: 'TechJini Solutions, Bengaluru',
					},
					content: [
						'Environment: MySQL, PHP, HTML, CSS, Jquery, amChart',
						'Projects worked on:',
						'Coupons System (MySql, PHP, HTML, CSS, Jquery, HighCharts)',
						'eLearning System (PHP [Symfony], MySql, HTML, CSS, Jquery, amCharts): Developed Quiz module. Developed reports including one using amCharts',
						'Contest based application (PHP [Symfony], MySql, HTML, CSS, Jquery)'
					]
				},
				{
					header: {
						dates: '25-Jul-2007 – 14-Mar-2009',
						jobTitle: 'Senior Software Engineer',
						org: 'TLI Software, Bengaluru',
					},
					content: [
						'Environment:​ PHP, MySQL, HTML, CSS, Javascript, Jquery',
						'Worked​ as Full-time resource (3 months on-site and 3 months offsite), with Computer Methods I​nternational Corp, Toronto, Canada (www.cmic.ca), on JasperReports',
						'Developed web applications independently as per client requirements using PHP, MySql'
					]
				},
			]
		}
	}
	let currentSection = resume['profile'].title;
	let currentGroup = resume['skills'].groups[0].name
	let expdates = resume['exp'].expList[0].header.dates;
</script>

<main>
	<div class="info">
		<div>
			<div class="apptitle">SRIKANT GUDI</div>
			<div class="contact">
				{resume['info'].loc} | <email>{resume['info'].email}</email> | <phone>{resume['info'].phone}</phone>
			</div>
			<div class="pos">{resume['info'].pos}</div>
		</div>
	</div>
	<div class="subtitle txtcenter">Best viewed in Landscape mode or in Browser</div>
	<div class="section">
		<div class="sectiontitle" class:active={currentSection === resume['profile'].title} on:click={() => currentSection = resume['profile'].title}>{resume['profile'].title}</div>
		<ul class="current-section" class:active={resume['profile'].title===currentSection}>
			{#each resume['profile'].contents as content}
				<li>{content}</li>
			{/each}
		</ul>
	</div>
	<div class="section">
		<div class="sectiontitle" class:active={currentSection === resume['skills'].title} on:click={() => currentSection = resume['skills'].title}>{resume['skills'].title}</div>
		<ul class="current-section" class:active={currentSection === resume['skills'].title}>
			{#each resume['skills'].groups as group}
				<div class="section">
					<div class="group" on:click={() => currentGroup = group.name} class:active={currentGroup === group.name}>{group.name}</div>
					<ul class="groupinfo" class:active={currentGroup === group.name}>
						{#each group.values as group}
							<div class="skill">
								<span class="skillname">{group.skill}</span>
								<span><Stars nfill={group.rating} /></span>
							</div>
						{/each}
					</ul>
				</div>
			{/each}
		</ul>
	</div>
	<div class="section">
		<div class="sectiontitle" class:active={currentSection === resume['exp'].title} on:click={() => currentSection = resume['exp'].title}>{resume['exp'].title}</div>
		<ul class="current-section" class:active={currentSection === resume['exp'].title}>
			{#each resume['exp'].expList as xp}
				<div class="exp" class:active={xp.header.dates === expdates}>
					<div class="exptitle" class:active={xp.header.dates === expdates} on:click={() => expdates = xp.header.dates}>{xp.header.dates} | {xp.header.jobTitle} | {xp.header.org}</div>
					{#if xp.header.dates === expdates}
					<ul>
						{#each xp.content as xpitem}
						<li>{xpitem}</li>
						{/each}
					</ul>
					{/if}
				</div>
			{/each}
		</ul>
	</div>
</main>
