<script>
  import {mainOpt} from './store';
	import Topnav from './Topnav.svelte';
	import Profile from './Profile.svelte';
	import Skills from './Skills.svelte';
	import WorkHistory from './WorkHistory.svelte';
	import Academic from './Academic.svelte';

	let name = 'world';
	let tabs = [
		{key: 'profile', label: 'Profile', component: Profile},
		{key: 'skills', label: 'Technical Skills', component: Skills},
		{key: 'workhist', label: 'Work History', component: WorkHistory},
	];
	let curComp = tabs[0].component;
	
	const setComp = (tab) => {
		curComp = tab.component;
    $mainOpt = tab.key;
	}
  $: $mainOpt = 'profile';
</script>

<style>
  :root {
    background-color: lightblue;
  }

  #app {
		display: flex;
		flex-flow: column;
    width: 100%;
    margin: 0 auto;
    background-color: whitesmoke;
    overflow: hidden;
  }
	.content {
		box-shadow: 0 0 4px #999;
		display: flex;
		gap: 10px;
	}
	.component {
		flex: 1;
		overflow: hidden;
		height: 75vh;
		transition: all 0.5s;
		opacity: 0.6;
		margin-bottom: 1em;
		box-shadow: 0 0 4px #999999;
	}
	.component:hover {
		flex: 3;
		overflow-y: auto;
		opacity: 1;
	}
	.topnav {
		display: flex;
		align-items: center;
		padding: 10px;
		background-image: linear-gradient(#ccc, whitesmoke, #ccc);
		margin-bottom: 10px;
		height: 2em;
	}
	.title {
		font-size: 20px;
		text-transform: uppercase;
		font-family: Righteous;
	}
	.contact-item {
		font-size:12px;
		margin: 0 10px;
    font-family: Montserrat;
	}
	.btn-nav {
		display: flex;
		background-color: #ddd;
		align-items: center;
    justify-content: space-between;
		padding: 8px;
		font-size: 14px;
		transition: all 0.5s;
	}
	.content {
		box-shadow: 0 0 4px #999999;
		height: 100%;
		padding: 10px;
	}
  .position-title {
    font-family: Orbitron;
  }
	@media screen and (max-width: 420px) {
		:root {
			padding: 0 10px;
			overflow: unset;
		}
		#app {
			height: auto;
		}
		.btn-nav {
			display: flex;
			height: 30px;
			width: 90%;
			overflow: hidden;
			background-color: whitesmoke;
		}
    .tab-btn {
      font-size: 8px;
      width: 30%;
    }
		.content {
			display: grid;
			grid-template-columns: 1fr;
			gap: 10px;	
		}
		.component {
			height: 50vh;
		}
	}
</style>
<div id="app">
  <Topnav />
	<div class="content">
		<div class="component"><Profile /></div>
		<div class="component"><Skills /></div>
		<div class="component"><WorkHistory /></div>
		<div class="component"><Academic /></div>
	</div>
</div>
