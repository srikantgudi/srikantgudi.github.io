<script>
	import { Container, Radio, Row, Col, MaterialApp } from 'svelte-materialify';

	import Resume1 from './Resume1.svelte';
	import Resume2 from './Resume2.svelte';
  	
	let resumes = {
		"r1": Resume1,
		"r2": Resume2
	};
	let resume = 'r2';

	const setResume = (opt) => {
		console.log('setResume> opt:',opt);
		resume = opt;
	}
</script>

<MaterialApp theme={"light"}>
	<Container fluid>
		<Row dense>
			<Col md={2} sm={12}>
				<Radio bind:group={resume} class="ml-4" value="r1">
					<span class="text-h5">Resume with custom styles</span>
				</Radio>
				<Radio bind:group={resume} class="ml-4" value="r2">
					<span class="text-h5">Resume with Svelte-Materialify</span>
				</Radio>
			</Col>
			<Col md>
				<svelte:component this={resumes[resume]} />
			</Col>
		</Row>
	</Container>
</MaterialApp>

