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
			<Col md={6}>
				<h3>SRIKANT GUDI</h3>
				<h4>Senior FrontEnd Professional</h4>
			</Col>
			<Col md={6}>
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