<script>
  import {mainOpt} from './store';
  import Panel from './Panel.svelte';
  import Rating from './Rating.svelte';
  
  let name = 'Technical Skills'
  let skills = [
    {
      group: 'Frameworks',
      items: [
        { name: 'Angular', level: 8 },
        { name: 'Svelte', level: 7 },
        { name: 'VueJS', level: 7 },
        { name: 'React', level: 7 },
        { name: 'Stencil', level: 6 },
      ],
    },
    {
      group: 'Web Skills',
      items: [
        { name: 'JavaScript', level: 8 },
        { name: 'HTML5', level: 8 },
        { name: 'CSS3', level: 7 },
        { name: 'NodeJS', level: 6 },
        { name: 'SVG', level: 5 },
      ],
    },
    {
      group: 'Databases/ NoSQL',
      items: [
        { name: 'MySQL', level: 7 },
        { name: 'MongoDB', level: 6 },
      ],
    },
    {
      group: 'Others',
      items: [
        { name: 'Django', level: 5 },
        { name: 'Python', level: 4 },
      ],
    },
  ]
</script>

<style>
  .skillgroup {
    padding: 1vh 2vw;
    box-shadow: 0 2px 4px #999999;
    margin-bottom: 10px;
  }
</style>

<div class="sectiontitle">Technical Skills</div>
<div style="padding: 0 4vw;">
  {#each skills as skill}
    <div>
      <div class="sectionsubtitle">{skill.group}</div>
      <div class="skillgroup">
        {#each skill.items as item}
          <Rating text={item.name} level={item.level} />
        {/each}
      </div>
    </div>
  {/each}
</div>
