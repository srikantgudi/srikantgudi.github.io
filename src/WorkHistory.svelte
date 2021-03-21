<script>
  import {mainOpt} from './store';
  import Panel from './Panel.svelte';
  
  let expList = [
    {
      header: {
        dates: '16-Jun-2016 to present',
        jobTitle: 'Project Lead - System',
        org: 'Mphasis, Bengaluru',
      },
      content: [
        'Currently working as Lead frontend developer with Schneider Electric using Svelte. Created web components using StencilJS',
        'Worked offshore in Bengaluru with a banking conglomerate on  projects in Angular and React',
        'Worked onsite in Glasgow, UK with a banking conglomerate on Angular based projects',
        'Developed UI for a POC for Digital Readiness Analysis Tool to create a survey questionnaire for various categories using Angular, Material Design, HTML5, CSS3, JavaScript, API integration',
        'Developed UI for client in Insurance domain using React, Material-UI, HTML5, CSS3, JavaScript, IndexedDB',
        'Worked offshore at client-side with Schneider Electric on Management Dashboard using Angular 1.x',
      ],
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
        'Integrated APIs in the frontend code',
      ],
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
        'Used Photoshop to slice images',
      ],
    },
    {
      header: {
        dates: 'Apr-2014 to Jun-2014',
        jobTitle: 'Senior AngularJS Developer',
        org: 'Satsyil, VA, USA (Remote work)',
      },
      content: [
        'Worked remotely as senior UI developer using AngularJS technology',
        'Modified admin-side modules and screen layouts and created new ones as required',
      ],
    },
    {
      header: {
        dates: '23-Nov-2011 – 07-Mar-2014',
        jobTitle: 'Senior Software Developer (Consultant)',
        org:
          'Tejas Systems / SUNSYSTEMS, Bengaluru :: Client: MModal Global Services Pvt Ltd',
      },
      content: [
        'Environment: PHP, MySQL, Jquery, Fancybox, Fusioncharts, HTML, CSS (Bootstrap), AngularJS',
        'modified client-side and admin-side scripts',
        'created animated presentation of iPad application using Jquery and Jquery-cycle',
        'created presentation of mobile application in Powerpoint',
        'created UI for password management using AngularJS',
      ],
    },
    {
      header: {
        dates: '12-Feb-2010 –22-Sep-2011',
        jobTitle: 'Senior Software Engineer',
        org: 'TechJini Solutions, Bengaluru',
      },
      content: [
        'Environment: MySQL, PHP, HTML, CSS, Jquery, amChart',
        'Projects worked on:',
        'Coupons System (MySql, PHP, HTML, CSS, Jquery, HighCharts)',
        'eLearning System (PHP [Symfony], MySql, HTML, CSS, Jquery, amCharts): Developed Quiz module. Developed reports including one using amCharts',
        'Contest based application (PHP [Symfony], MySql, HTML, CSS, Jquery)',
      ],
    },
    {
      header: {
        dates: '25-Jul-2007 – 14-Mar-2009',
        jobTitle: 'Senior Software Engineer',
        org: 'TLI Software, Bengaluru',
      },
      content: [
        'Environment:​ PHP, MySQL, HTML, CSS, Javascript, Jquery',
        'Worked​ as Full-time resource (3 months on-site and 3 months offsite), with Computer Methods I​nternational Corp, Toronto, Canada (www.cmic.ca), on JasperReports',
        'Developed web applications independently as per client requirements using PHP, MySql',
      ],
    },
  ];
  let curExpIdx = 0;
  $: curExp = expList[curExpIdx];
</script>

<style>
  .org-name, .exp-period {
    font-size: 14px;
  }
  .job-title {
    font-family: Montserrat;
    background-color: #495057;
    color: #f8f9fa;
    padding: 10px;
  }
  .org-name {
    font-family: Montserrat;
    box-shadow: 0 0 4px #495057;
    padding: 1vh 2vw;
  }

  .exp {
    display: flex;
    flex-flow: column;
    height: auto;
    margin: 1vh 4vw;
    box-shadow: 0 2px 2px #999999;
  }
  .details {
    margin: 1vh 4vw;
    font-family: Montserrat;
    font-size: 1vw;
  }
  .exp:hover {
    box-shadow: 0 0 10px #666666;
    font-size: 110%;
    transition: all 1s;
    background-color: lightcyan;
    border-radius: 30px;
  }
  .exp:hover > .job-title {
    border-radius: 30px 30px 0 0;
    padding-left: 2vw;
  }
  @media screen and (max-width: 639px) {
  }
</style>

<div class="resume-section">
  <div class="sectiontitle">WORK EXPERIENCE</div>
  {#each expList as exp, idx}
    <div class="exp">
      <div class="job-title">
        {exp.header.jobTitle} &raquo; <span class="exp-period">{exp.header.dates}</span>
      </div>
      <div class="org-name">
        {exp.header.org}
      </div>
      <div class="details">
        <ul>
          {#each exp.content as text}
            <li>{text}</li>
          {/each}
        </ul>
      </div>
    </div>
  {/each}
</div>