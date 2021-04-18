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
<MaterialApp {theme} style="background: lightcyan">
	<Container fluid>
		<Card class="text-center">
			<div class="title name righteous white-text page grey">
				SRIKANT GUDI
			</div>
			<div class="title position grey grey-text lighten-4">
				Senior FrontEnd Professional
			</div>
		</Card>
		<Card dense>
			<CardTitle class="text-h3 blue white-text">About me</CardTitle>
			<CardText class="text-h6">
				<div class="ml-8">Specialized in:</div>
				<div class="ml-16">
					<div>Svelte, VueJS, React, Angular, StencilJS, NodeJS, JavaScript, TypeScript, HTML5, CSS3, JSON, SVG</div>
				</div>
				<div class="ml-8">Familiar with:</div>
				<div class="ml-16">Python-Django, Laravel</div>
				<Row dense class="content-item">
					<Col md={3} sm={6} cols={12}><a href="mailto:srikantgudi@gmail.com">Mail me!</a></Col>
					<Col md={3} sm={6} cols={12}>+91 829 665 6336</Col>
					<Col md={3} sm={6} cols={12}><a href="https://linkedin.com/in/srikantgudi-blr">LinkedIn Profile</a></Col>
					<Col md={3} sm={6} cols={12}>Skype: srikantgudi</Col>
				</Row>
			</CardText>
        </Card>
		<Card>
			<CardTitle class="text-h3 blue white-text">Profile</CardTitle>
			<CardText>
				{#each data.profile as text}
					<div class="content-item">
						{text}
					</div>
				{/each}
			</CardText>
		</Card>
		<Card>
			<CardTitle class="text-h3 blue white-text">Technical Skills</CardTitle>
			<CardText class="ml-8 mr-8">
				<ExpansionPanels>
				{#each Object.keys(data.skills) as grouptitle}
				<ExpansionPanel>
					<div slot="header" class="indigo white-text pa-4">{grouptitle.toUpperCase()}:&nbsp;{data.skills[grouptitle].length}</div>
					<Row class="ml-2 mr-2 pa-4 skills">
						{#each data.skills[grouptitle] as skill}
							<Col md={3} sm={6} cols={12}>
								<Card>
									<CardTitle>
										{skill.name}
									</CardTitle>
									<CardText>
										<ProgressLinear height="30px" value={75} />
									</CardText>
								</Card>
							</Col>
						{/each}
					</Row>
				</ExpansionPanel>
				{/each}
			</ExpansionPanels>
			</CardText>
		</Card>
		<Card>
			<CardTitle class="text-h3 blue white-text">Work Experience</CardTitle>
			<CardText>
				<ExpansionPanels class="mr-10">
					{#each data.exp as xp}
					<ExpansionPanel>
						<div slot="header" class="text-h6 brown white-text pl-2 pr-2">
							{xp.dates}: {xp.jobTitle}
						</div>
						<Card>
							<CardTitle>
								{xp.technology}
							</CardTitle>
							<CardText>
								{#each xp.content as text}
									<li>
										&raquo; {text}
									</li>
								{/each}
							</CardText>
						</Card>
					</ExpansionPanel>
					{/each}
				</ExpansionPanels>
			</CardText>
		</Card>
	</Container>
</MaterialApp>