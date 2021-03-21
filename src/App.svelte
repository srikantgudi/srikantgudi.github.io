<script>
	import Profile from './Profile.svelte';
	import Skills from './Skills.svelte';
	import WorkHistory from './WorkHistory.svelte';
	import Academic from './Academic.svelte';
	
	let name = 'Srikant Gudi';
	let comps = {
		'profile': {title: 'Profile', comp: Profile},
		'skills': {title: 'Technical Skills', comp: Skills},
		'workexp': {title: 'Work History', comp: WorkHistory},
	};
	let showContact = false;
	let compKey = 'skills';
	let curComp = Profile;
	$: curComp = comps[compKey].comp;
</script>

<style>
	.compnav {
		display: flex;
		flex-flow: row wrap;
		justify-content: space-around;
		margin: 10px 0;
		background: linear-gradient(lightcyan,lightblue,lightcyan);
		padding: 5px;
	}
	.compbtn {
		border: none;
		padding: 10px;
		border-radius: 4px;
		box-shadow: 0 2px 4px #003;
		margin: 0 4px 4px 0;
		display: none;
		cursor: pointer;
		font-family: Montserrat;
		font-size: 1.5vw;
		font-weight: 600;
		background: linear-gradient(lightgrey,whitesmoke,grey);
	}
	.compbtn.show {
		display: block;
		min-width: 30%;
	}
	.contact-btn {
		border-radius: 50%;
		width: 30px;
		height: 30px;
		cursor: pointer;
		position: absolute;
		top: 1vh;
		left: 25%;
		display: block;
	}
	.contact-btn:hide {
		display: none;
	}
	.contact-info {
		display: none;
		width: fit-content;
		height: fit-content;
		transition: all 1s;
	}
	.contact-info.active {
		display: flex;
		flex-flow: column;
		position: absolute;
		top: 1vh;
		left: 25%;
		border-radius: 2vw 2vh;
		box-shadow: 0 2px 2px #333333;
		background: linear-gradient(lightblue,lightcyan);
	}
	.contact-item {
		font-size: 18px;
		margin: 4px;
		min-width: 30%;
	}
	.page-title {
		font-size: 3vw;
		font-weight: 600;
		font-family: Righteous;
		text-transform: uppercase;
		text-shadow: 4px -2px 10px teal;
		color: navy;
		padding: 1vh 5vw;
		border-radius: 20px 20px 0 0;
		box-shadow: 0 2px 10px #009;
		background: linear-gradient(lightblue,lightcyan);
	}
	.position-title {
		font-family: Orbitron;
		font-weight: 600;
		font-size: 1.5vw;
		margin: 1vh 10vw;
		padding: 10px;
		border-radius: 20px 20px 0 0;
		box-shadow: 0 2px 10px #009;
		background: linear-gradient(lightcyan,lightblue);
	}
	.topnav {
		display: flex;
		flex-flow: column;
		align-items: center;
		justify-content: space-around;
	}
	@keyframes letterspace {
		from {letter-spacing: 1px; color: #333;}
		to {letter-spacing:10px; color: #ddd;}
	}
	.cur-comp {
		box-sizing: border-box;
		font-family: monospace;
		font-size: 2vw;
		letter-spacing: 2px;
		font-weight: 600;
		display: flex;
		justify-content: space-around;
		animation: letterspace 2s ease-in infinite alternate-reverse;
	}
	.close-btn {
		width: 30px;
		cursor: pointer;
		border-radius: 2vw 2vh;
	}
	@media screen and (max-width: 639px) {
		.topnav {
			flex-flow: column;
			justify-content: space-around;
		}
		.contact-btn, .contact-info.active {
			left: 5vw;
		}
		.contact-item {
			font-size: 12px;
		}
	}
</style>

<div id="app">
	<button class="contact-btn" on:click={() => {showContact=true}} class:hide={showContact}>
		?
	</button>
	<div class="contact-info" class:active={showContact}>
		<button class="close-btn" on:click={() => {showContact = false}}>
			&times;
		</button>
		<div class="contact-item">Bengaluru, India</div>
		<div class="contact-item">srikantgudi@gmail.com</div>
		<div class="contact-item">+91 829 665 6336</div>
	</div>
	<div class="topnav">
		<div class="page-title">{name}</div>
		<div class="position-title" >
			Senior Frontend Professional
		</div>
	</div>
	<div class="compnav">
		{#each Object.keys(comps) as key}
		<button class="compbtn" class:show={key !== compKey} on:click={() => {compKey=key}}>{comps[key].title}</button>
		{/each}	
	</div>

	<div class="cur-comp">{comps[compKey].title}</div>
	<div class="content">
		<svelte:component this={comps[compKey].comp} />
	</div>
</div>
