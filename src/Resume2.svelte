<script>
	import {data} from './data/data';
	import {
		MaterialApp, Card, CardTitle, CardText, CardActions,
		ExpansionPanels, ExpansionPanel, 
		ProgressLinear, Container, Row, Col
	} from 'svelte-materialify';
import App from './App.svelte';
	let theme = 'light';
</script>
<MaterialApp {theme}>
	<Container fluid>
		<Card dense class="panel">
			<div class="title name righteous white-text page grey">
				SRIKANT GUDI
			</div>
			<div class="title position grey grey-text lighten-4">
				Senior FrontEnd Professional
			</div>
		</Card>
		<Card dense class="panel">
			<CardTitle class="panel-title arialrounded text-h4 blue white-text">About me</CardTitle>
			<CardText class="text-h6">
				<div class="ml-8">Specialized in:</div>
				<div class="ml-16">
					<div>Svelte, VueJS, React, Angular, StencilJS, NodeJS, JavaScript, TypeScript, HTML5, CSS3, JSON, SVG</div>
				</div>
				<div class="ml-8">Familiar with:</div>
				<div class="ml-16">Python-Django, Laravel</div>
				<Row dense class="content-item">
					<Col md={3} sm={6} cols={12}>srikantgudi@gmail.com</Col>
					<Col md={3} sm={6} cols={12}>+91 829 665 6336</Col>
					<Col md={3} sm={6} cols={12}><a class="link" href="https://linkedin.com/in/srikantgudi-blr">LinkedIn Profile</a></Col>
					<Col md={3} sm={6} cols={12}>Skype: srikantgudi</Col>
				</Row>
			</CardText>
        </Card>
		<Card dense class="panel">
			<CardTitle class="panel-title arialrounded text-h4 blue white-text">Profile</CardTitle>
			<CardText class="montserrat">
				{#each data.profile as text}
					<Card dense class="ml-8 mb-1 mr-12">
						<CardText class="text-h6">
							{text}
						</CardText>
					</Card>
				{/each}
			</CardText>
		</Card>
		<Card dense class="panel">
			<CardTitle class="panel-title arialrounded text-h4 blue white-text">Technical Skills</CardTitle>
			<CardText class="ml-8 mr-8">
				{#each Object.keys(data.skills) as grouptitle}
					<Row dense class="groupname white-text text-h5 mr-10 pa-4">{grouptitle.toUpperCase()}</Row>
					<Row dense class="ml-2 mr-16 pr-16 skills">
						{#each data.skills[grouptitle] as skill}
							<Col md={4} sm={6} cols={12}>
								<ProgressLinear class='text-h5' color='cyan' backgroundColor="grey" height="40px" value={75}>
									{skill.name}
								</ProgressLinear>
							</Col>
						{/each}
					</Row>
				{/each}
			</CardText>
		</Card>
		<Card dense class="panel">
			<CardTitle class="panel-title arialrounded text-h4 blue white-text">
			  Demo Apps
			</CardTitle>
			<CardText class="mr-8 demoapps">
				{#each data.demoapps as app}
					<Card dense class="demoapp">
						<CardTitle>
							<a class="demoapp-title link" target="_blank" href={`https://${app.appname}.netlify.app`}>
								{app.title}
							</a>
						</CardTitle>
						<CardText class="montserrat">
							<div>Technology: {app.technology}</div>
							<div class="text-h6">{app.description}</div> 
						</CardText>
					</Card>
				{/each}
			</CardText>
		</Card>
		<Card dense class="panel">
			<CardTitle class="panel-title arialrounded text-h4 blue white-text">Work Experience</CardTitle>
			<CardText class="ml-2 mr-12">
				{#each data.exp as xp}
					<Card>
						<CardTitle class="mt-2 mb-1">
							{xp.dates}: {xp.jobTitle}
						</CardTitle>
					</Card>
					<Card class="ml-10 mr-4 montserrat">
						<CardText>
							{xp.technology}
							{#each xp.content as text}
								<li>
									{text}
								</li>
							{/each}
						</CardText>
					</Card>
				{/each}
			</CardText>
		</Card>
	</Container>
</MaterialApp>