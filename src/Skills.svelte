<script>
  import SkillLevel from './SkillLevel.svelte';
  
  let name = 'Technical Skills'
  let skills = [
    // {
    //   group: 'Frameworks',
    //   items: [
    //     { name: 'Svelte', level: 85 },
    //     { name: 'Angular', level: 80 },
    //     { name: 'VueJS', level: 80 },
    //     { name: 'React', level: 75 },
    //     { name: 'Stencil', level: 70 },
    //   ],
    // },
    // {
    //   group: 'Web Skills',
    //   items: [
    //     { name: 'JavaScript/TypeScript', level: 85 },
    //     { name: 'HTML5', level: 85 },
    //     { name: 'CSS3', level: 85 },
    //     { name: 'NodeJS', level: 75 },
    //     { name: 'SVG', level: 75 },
    //   ],
    // },
    // {
    //   group: 'Databases/ NoSQL',
    //   items: [
    //     { name: 'MySQL', level: 75 },
    //     { name: 'MongoDB', level: 65 },
    //   ],
    // },
    // {
    //   group: 'Others',
    //   items: [
    //     { name: 'Django', level: 60 },
    //     { name: 'Python', level: 55 },
    //   ],
    // },

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
    height: 50vmin;
    overflow-y: auto;
  }
  .skillgroup {
    width: inherit;
    box-shadow: 0 2px 0 #999999;
    margin-bottom: 1vmax;
    padding: 1vmax;
  }
  .skillgroup:last-child {
    border-bottom: none;
  }
  .grouptitle {
    background-color: whitesmoke;
    padding: 5px;
    margin: 0 0 0.5vmax;
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
      <div class="grouptitle">{skill.group}:</div>
      <div>{skill.items}</div>
    </div>
  {/each}
</div>
