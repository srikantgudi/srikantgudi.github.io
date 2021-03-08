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
  let currGroup = skills[0].group;
</script>

<Panel showcontent={$mainOpt === 'skills'}>
  <div slot="title" on:click={() => {$mainOpt = 'skills'}}>Technical Skills</div>
  <div slot="content">
    {#each skills as skill}
      <Panel hdrbg="lightblue" hdrclr="#333333">
        <div slot="title">{skill.group}</div>
        <div slot="content">
          {#each skill.items as item}
            <Rating text={item.name} level={item.level} />
          {/each}
        </div>
      </Panel>
    {/each}
  </div>
</Panel>
