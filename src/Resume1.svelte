<script>
	import Profile from './Profile.svelte';
	import TechSkills from './TechSkills.svelte';
	import Demoapps from './Demoapps.svelte';
	import WorkHistory from './WorkHistory.svelte';
</script>
<div class="resume">
	<div class="topnav">
		<div class="title name">
			SRIKANT GUDI
		</div>
		<div class="title position">
			Senior FrontEnd Professional
		</div>
        <div class="text-center">
            <div class="content-item">
                <div>Specialized in:</div>
                <ul>
                    <li>
                        Svelte, VueJS, React, Angular, StencilJS, NodeJS
                    </li>
                    <li>
                        JavaScript, TypeScript, HTML5, CSS3, JSON, SVG
                    </li>
                </ul>
            </div>
            <div class="content-item">
                Familiar with: Python-Django, Laravel
            </div>
            <div class="content-item">
                srikantgudi@gmail.com | +91 829 665 6336
            </div>
        </div>
	</div>
	<div>
		<Profile />
	</div>
	<div>
		<TechSkills />
	</div>
	<div>
		<Demoapps />
	</div>
	<div>
		<WorkHistory />
	</div>
</div>