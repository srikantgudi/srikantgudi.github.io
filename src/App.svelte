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

<style>
	.topbar {
		position:fixed;
		z-index: 999;
		height:4em;
		top: 0;
		margin-bottom: 10px;
		left: 0;
		right: 0;
		display: flex;
		align-items: center;
		padding: 0 5em;
	}
	.resume-view {
		margin-top:4em;
	}
</style>

<MaterialApp theme={"light"}>
	<Container fluid>
		<div class="topbar white elevation-4">
			<div>Choose resume to view:</div>
			<Radio bind:group={resume} class="ml-4" value="r1">
				<span class="text-h5">Resume with custom styles</span>
			</Radio>
			<Radio bind:group={resume} class="ml-4" value="r2">
				<span class="text-h5">Resume with Svelte-Materialify</span>
			</Radio>
		</div>
		<div dense class="resume-view">
			<svelte:component this={resumes[resume]} />
		</div>
	</Container>
</MaterialApp>

