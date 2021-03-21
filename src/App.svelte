<script>
	import Profile from './Profile.svelte';
	import Skills from './Skills.svelte';
	import WorkHistory from './WorkHistory.svelte';
</script>
<div id="app">
	<div class="topnav">
		<div>
			<div class="page-title">Srikant Gudi</div>
			<div class="position-title" >
				Senior Frontend Professional
			</div>
		</div>
		<div class="contact-info">
			<div class="contact-item">Bengaluru, India</div>
			<div class="contact-item">srikantgudi@gmail.com</div>
			<div class="contact-item">+91 829 665 6336</div>
			<div class="contact-item"><a href="https://www.linkedin.com/in/srikantgudi-blr" target="_blank">LinkedIN Profile</a></div>
			<div class="contact-item">Skype: srikantgudi</div>
		</div>
	</div>

	<div class="content">
		<Profile />
		<Skills />
		<WorkHistory />
	</div>
</div>
