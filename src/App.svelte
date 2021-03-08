<script>
  import {mainOpt} from './store';
	import Profile from './Profile.svelte';
	import Skills from './Skills.svelte';
	import WorkHistory from './WorkHistory.svelte';
	
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
    width: 80%;
    margin: 0 auto;
    background-color: whitesmoke;
    height: 100%;
    overflow: hidden;
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
	}
</style>
<div id="app">
  <div class="topnav">
    <div class="title">
      Srikant Gudi
    </div>
    <div class="contact-item">
      Bengaluru, India | +91 829 665 6336 | srikantgudi@gmail.com
    </div>
    <div class="position-title">
      Senior Frontend Engineer
    </div>
  </div>
  <div class="btn-nav">
    {#each tabs as tab}
    <button class="tab-btn" on:click={() => setComp(tab)}>
      {tab.label}
    </button>
    {/each}
  </div>
  <div class="content">
    <svelte:component this={curComp} />
  </div>
</div>
