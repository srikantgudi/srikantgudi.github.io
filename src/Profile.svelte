<script>
  import {mainOpt} from './store';
  import Panel from './Panel.svelte';
</script>

<Panel>
  <div slot="title" on:click={() => {$mainOpt = 'profile'}}>Profile</div>
  <div slot="content">
    <Panel hdrbg="#eeeeee" hdrclr="#666">
      <div slot="title">About me</div>
      <div slot="content">
        <ul>
          <li>
            Senior software professional with over 20 years of experience in various
            technologies
          </li>
          <li>
            From April 2014 into frontend development using Angular, Svelte, Stencil,
            React, VueJS, NodeJS
          </li>
          <li>
            Nov 2005 to March 2014: into Web development using PHP, MySQL, JQuery,
            JavaScript, HTML, CSS
          </li>
          <li>
            Prior to Nov 2005: Application development using FoxPro, Visual Basic,
            PowerBuilder
          </li>
          <li>Can create POCs, presentations, and wireframes.</li>
        </ul>
      </div>
    </Panel>
    <Panel hdrbg="#eeeeee" hdrclr="#666">
      <div slot="title">Academic</div>
      <div slot="content">
        <ul>
          <li>Master in Computer Management</li>
          <li>Bachelor of Commerce</li>
        </ul>
      </div>
    </Panel>
  </div>
</Panel>
