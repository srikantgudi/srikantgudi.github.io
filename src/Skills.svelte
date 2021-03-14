<script>
  import SkillLevel from './SkillLevel.svelte';
  
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
    gap: 10px;
  }
  .skillgroup {
    width: inherit;
    box-shadow: 0 2px 4px #999999;
    margin-bottom: 1vmax;
    padding: 5px;
  }
  .skillgrouptitle {
    box-sizing: border-box;
    background-color: #cccccc;
    border-radius: 0 0 4px 4px;
    padding: 5px;
  }
  .skillname {
    font-family: Montserrat;
    font-size: 16px;
    padding: 5px;
  }
  @media screen and (max-width: 420px) {
    .skills {
      display: block;;
      height: inherit;
    }
  }
</style>

<div class="skills">
  {#each skills as skill}
    <div class="skillgroup">
      <div class="skillgrouptitle">{skill.group}:</div>
      <div class="skillname">{skill.items}</div>
    </div>
  {/each}
</div>
