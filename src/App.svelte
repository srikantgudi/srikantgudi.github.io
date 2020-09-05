<script>
	let profiles = [
		'Senior software professional with over 20 years of experience',
	  '2005 - 2013: Web development experience using PHP, MySQL',
	  '2014 onwards into UI development',
	  'Can create wire-frames, POCs'
	];
	let skills = [
		'HTML5, CSS3, JavaScript',
		'Angular, Svelte, Stencil, React, Vue, Nuxt',
		'MySql, Mongodb',
		'Git, Bitbucket, Confluence'
	]
</script>

<main id="my-app">
	<div id="top-nav">
		<div id='name'>
			<div class='title'>
				Srikant Gudi
			</div>
			<div>
				Bengaluru, India
			</div>
		</div>
		<div id='contact'>
			<div class="mail">srikantgudi@gmail.com</div>
			<div>+91 829-665-6336</div>
		</div>
	</div>
	<div id="profile">
		<div class='box'>
			<h2>Summary</h2>
			<ul>
			{#each profiles as line}
				<li>{line}</li>
			{/each}
			</ul>
		</div>
		<div class='box'>
			<h2>Skills</h2>
			{#each skills as skill}
				<li>{skill}</li>
			{/each}
		</div>
	</div>
</main>
<style>
	* {
		margin: 0;
		font-family: Helvetica;
	}
	#my-app {
		width: 90vw;
		margin: 0 auto;
		font-family: Helvetica;
	}
	#top-nav {
		box-shadow: 0 0 4px #999999;
		padding: 4px 10px;
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-gap: 10px;
		grid-template-areas: 'name contact';
		background-color: #eeeeee;
	}
	.box {
		box-shadow: 0 0 4px #999999;
	}
	#name {
		grid-area: name;
	}
	#name .title {
		font-family: cursive;
		font-size: 30px;
		font-weight: 600;
	}
	#contact {
		grid-area: contact;
		text-align: right;
		line-height: 30px;
	}
	#contact .mail {
		text-decoration: none;
	}
	#profile {
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-gap: 20px;
		margin: 10px auto;
	}
	#profile > div {
		padding: 8px 20px;
	}
	li {
		list-style: none;
		line-height: 1.5;
	}
	li:before {
		content: '> ';
	}
</style>
