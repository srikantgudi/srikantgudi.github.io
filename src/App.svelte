<script>
  import { Container, Row, Col, MaterialApp } from 'svelte-materialify';

	import Profile from './Profile.svelte';
	import Contact from './Contact.svelte';
	import TechSkills from './TechSkills.svelte';
	import Demoapps from './Demoapps.svelte';
	import WorkHistory from './WorkHistory.svelte';

	let comp = 1;
</script>

<Container fluid class="app">
	<div class="topnav">
		<div class="title name">SRIKANT GUDI</div>
		<div class="title profession">Senior FrontEnd Engineer</div>
		<Contact />
	</div>
	<div class="app-content">
		<div>
			<Profile/>
		</div>
		<div>
			<TechSkills/>
		</div>
		<div>
			<Demoapps/>
		</div>
		<div>
			<WorkHistory/>
		</div>
	</div>
</Container>
