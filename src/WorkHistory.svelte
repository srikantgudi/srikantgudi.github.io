<script>
    let expList = [
		{
			header: {
				dates: '16-Jun-2016 to present',
				jobTitle: 'Project Lead - System',
				org: 'Mphasis, Bengaluru',
			},
			content: [
                'Currently working as Lead developer in Design System with Schneider Electric',
				'Worked offshore in Bengaluru with a banking conglomerate on  projects in Angular and React',
				'Worked onsite in Glasgow, UK with a banking conglomerate on Angular based projects',
				'Developed UI for a POC for Digital Readiness Analysis Tool to create a survey questionnaire for various categories using Angular, Material Design, HTML5, CSS3, JavaScript, API integration',
				'Developed UI for client in Insurance domain using React, Material-UI, HTML5, CSS3, JavaScript, IndexedDB',
				'Worked offshore at client-side with Schneider Electric on Management Dashboard using Angular 1.x',
			]
		},
		{
			header: {
				dates: '15-Aug-2015 to 14-Jan-2016',
				jobTitle: 'Senior AngularJS Developer',
				org: 'Pandera Solutions India Pvt Ltd, Bengaluru',
			},
			content: [
				'Worked in Angular on various projects',
				'Created sub-components for re-use',
				'Interacted with client-side developers to understand the requirements',
				'Integrated APIs in the frontend code'
			]
		},
		{
			header: {
				dates: '20-Aug-2014 to 22-Jan-2015',
				jobTitle: 'Senior Software Developer',
				org: 'Basil Communications Pvt Ltd, Bengaluru',
			},
			content: [
				'Created HTML mockups for various applications',
				'Interacted with designers to understand the designs',
				'Used Photoshop to slice images'
			]
		}
	];
	let curExp = expList[0];
</script>

<style>
    .exp {
        display: grid;
        grid-template-columns: 1fr 3fr;
        grid-gap: 10px 20px;
    }
    .expdate {
        box-shadow: 0 2px 4px #666666;
        border-radius: 8px 8px 0 0;
        padding: 5px 10px;
        cursor: pointer;
        background-color: lightblue;
        margin-bottom: 4px;
    }
    .expdate.active {
        background-color: darkslategrey;
        color: #f9f9f9;
    }
</style>

<main class="exp">
    <div>
        {#each expList as exp}
            <div class="expdate" class:active={curExp === exp} on:click={() => curExp = exp}>{exp.header.dates}</div>
        {/each}
    </div>
    <div>
        <h3>{curExp.header.dates} :: {curExp.header.jobTitle} {curExp.header.org}</h3>
        <ul>
            {#each curExp.content as detail}
            <li>{detail}</li>
            {/each}
        </ul>
    </div>
</main>