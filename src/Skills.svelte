<script>
  import SkillLevel from './SkillLevel.svelte';
  
  let name = 'Technical Skills'
  let skills = [
    {
      group: 'Frameworks',
      items: [
        { name: 'Svelte', level: 85 },
        { name: 'Angular', level: 80 },
        { name: 'VueJS', level: 80 },
        { name: 'React', level: 75 },
        { name: 'Stencil', level: 70 },
      ],
    },
    {
      group: 'Web Skills',
      items: [
        { name: 'JavaScript', level: 85 },
        { name: 'HTML5', level: 85 },
        { name: 'CSS3', level: 85 },
        { name: 'NodeJS', level: 75 },
        { name: 'SVG', level: 75 },
      ],
    },
    {
      group: 'Databases/ NoSQL',
      items: [
        { name: 'MySQL', level: 75 },
        { name: 'MongoDB', level: 65 },
      ],
    },
    {
      group: 'Others',
      items: [
        { name: 'Django', level: 60 },
        { name: 'Python', level: 55 },
      ],
    },
  ]
</script>

<style>
  .skillgroup {
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    padding: 1vh 2vw;
    box-shadow: 0 2px 4px #999999;
    margin-bottom: 10px;
  }
</style>

<div class="sectiontitle">Technical Skills</div>
<div class="inner-content-body">
  {#each skills as skill}
    <div>
      <div class="sectionsubtitle">{skill.group}</div>
      <div class="skillgroup">
        {#each skill.items as item}
        <SkillLevel label={item.name} rating={item.level} />
        {/each}
      </div>
    </div>
  {/each}
</div>
