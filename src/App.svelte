<script>
  import { Container, Row, Col, MaterialApp } from 'svelte-materialify';

	import Topnav from './Topnav.svelte';
	import Profile from './Profile.svelte';
	import Contact from './Contact.svelte';
	import TechSkills from './TechSkills.svelte';
	import Demoapps from './Demoapps.svelte';
	import WorkHistory from './WorkHistory.svelte';

	let comp = 1;
</script>

<Container fluid class="app">
	<Topnav />
	<Profile/>
	<TechSkills/>
	<Demoapps/>
	<WorkHistory/>
</Container>
