<script>
	import { Container, Button, Row, Col, MaterialApp } from 'svelte-materialify';

	import Resume1 from './Resume1.svelte';
	import Resume2 from './Resume2.svelte';
  	
	let resumes = {
		"r1": Resume1,
		"r2": Resume2
	};
	let resume = 'r1';

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
	.resume-btn {
		background-color: whitesmoke;
		padding: 1em;
		color: #000;
	}
	.resume-btn.active {
		background: linear-gradient(lightblue, lightcyan, lightblue);
	}
</style>

<MaterialApp theme={"light"}>
	<Container fluid>
		<div class="topbar white elevation-4">
			<div>Choose resume to view:</div>
			<Button class="text-h5 mr-2" on:click={() => setResume('r1')}>
				<div class="resume-btn" class:active={resume==='r1'}>Resume with custom styles</div>
			</Button>
			<Button class="text-h5" on:click={() => setResume('r2')}>
				<div class="resume-btn" class:active={resume==='r2'}>Resume with Svelte-Materialify</div>
			</Button>
		</div>
		<div dense class="resume-view">
			<svelte:component this={resumes[resume]} />
		</div>
	</Container>
</MaterialApp>

