<script>
  import {data} from './data/data';
  
  let name = 'Technical Skills'
  let skills = [
    {group: 'Frameworks', items: 'Angular, Svelte, VueJS, React, Stencil'},
    {group: 'Web Skills', items: 'JavaScrip, TypeScript, HTML5, CSS3, SVG'},
    {group: 'Libraries', items: 'Bootstrap, Angular-Material, React-UI, Vuetify, Buefy'},
    {group: 'Agile Methodology', items: 'Scrum, Sprint, JIRA, GIT, Confluence'},
    {group: 'Operating Systems', items: 'Windows, MacOS, Linux (Ubuntu, Mint)'},
    {group: 'Coding Tools', items: 'VS Code, IntelliJ, Nodepad++'},
    {group: 'Others', items: 'Python-Django, Cansandra'},
    {group: 'Online coding', items: 'StackBlitz, CodeSandbox'},
  ]
</script>

<style>
  .skills {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 0 10px;
    height: auto;
  }
  .skillgroup {
    min-width: 30%;
    box-shadow: 0 2px 2px #666666;
    margin-bottom: 1vmax;
    border-radius: 10px 10px 0 0;
    padding: 1vh 0;
  }
  .groupname {
    background: linear-gradient(#123456,#654321);
    padding: 1vh 1vw;
    color: white;
    border-radius: 0 0 10px 10px;
  }
  .skillname {
    font-family: Montserrat;
    font-size: 14px;
    padding-left: 2vw;
    line-height: 1.5;
  }
  @media screen and (max-width: 420px) {
    .skills {
      grid-template-columns: 1fr 1fr;
    }
  }
</style>

<div class="skills">
  {#each data.skills as skill}
    <div class="skillgroup">
      <div class="groupname">
        {skill.group}
      </div>
      {#each skill.items as skillname}
        <div class="skillname">{skillname}</div>
      {/each}
    </div>
  {/each}
</div>
