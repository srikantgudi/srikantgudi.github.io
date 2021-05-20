<script>
  import { Container, Row, Col, MaterialApp } from 'svelte-materialify';

	import Profile from './Profile.svelte';
	import Contact from './Contact.svelte';
	import TechSkills from './TechSkills.svelte';
	import Demoapps from './Demoapps.svelte';
	import WorkHistory from './WorkHistory.svelte';
	
</script>

<MaterialApp>
	<Container>
		<Row>
			<Col md={12} cols={12} class="text-center">
				<div class="app-title">SRIKANT GUDI</div>
				<div class="profession-title">Senior FrontEnd Engineer</div>
			</Col>
		</Row>
		<Row>
			<Col cols={12}>
				<Contact />
			</Col>
		</Row>
		<Row>
			<Col cols={12}>
				<Profile />
			</Col>
		</Row>
		<Row>
			<Col cols={12}>
				<TechSkills />
			</Col>
		</Row>
		<Row>
			<Col cols={12}>
				<Demoapps />
			</Col>
		</Row>
		<Row>
			<Col cols={12}>
				<WorkHistory />
			</Col>
		</Row>
	</Container>
</MaterialApp>