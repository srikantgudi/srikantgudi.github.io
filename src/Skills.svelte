<script>
  import Panel from './Panel.svelte'

  let skills = [
    {
      group: 'Web Technologies',
      items: [
        { name: 'HTML5', rating: 8 },
        { name: 'CSS3', rating: 8 },
        { name: 'JavaScript', rating: 8 },
      ],
    },
    {
      group: 'Frameworks/ Libraries',
      items: [
        { name: 'Angular', rating: 8 },
        { name: 'Svelte', rating: 8 },
        { name: 'Stencil', rating: 6 },
        { name: 'React', rating: 7 },
        { name: 'Vue', rating: 7 },
        { name: 'Nuxt', rating: 7 },
      ],
    },
    {
      group: 'Databases/ NoSQL',
      items: [
        { name: 'MySql', rating: 7 },
        { name: 'Mongodb', rating: 6 },
      ],
    },
    {
      group: 'Others',
      items: [
        { name: 'Git/ Bitbucket', rating: 7 },
        { name: 'Confluence', rating: 7 },
        { name: 'Visual Studio Code', rating: 8 },
        { name: 'IntelliJ', rating: 7 },
      ],
    },
  ]
  let selectedGroup = skills[0].group
</script>

<style>
  .skill-group {
    box-shadow: 0 0 2px #666666;
    margin-bottom: 4px;
    padding: 0 4px;
    display: grid;
    grid-template-columns: 2fr 3fr;
    align-items: center;
  }
  .group-name {
    font-size: 16px;
    background-color: darkslategrey;
    color: white;
    padding: 4px;
    cursor: pointer;
  }
  .skill {
    display: grid;
    grid-template-columns: 2fr 3fr;
    grid-gap: 4px 8px;
    margin: 4px 0;
  }
  .skill-name {
    font-size: 14px;
  }
  .txt-right {
    text-align: right;
  }
  .skill-list {
    background-color: lightcyan;
    padding: 4px;
    transition: all 1s ease-in;
  }
  .skill-list.active {
    display: block;
  }
  @media only screen and (max-width: 719px) {
    .skill-name,
    .group-name {
      font-size: 80%;
    }
  }
</style>

<Panel>
  <div slot="header">Technical Skills</div>
  <div slot="content">
    <div>
      {#each skills as skill}
        <div class="skill-group">
          <div class="group-name">{skill.group}</div>
          <div class="skill-list">
            {#each skill.items as item}
              <div class="skill">
                <span class="skill-name txt-right">{item.name}:</span>
                <span>
                  <svg height="20px" width="100">
                    <rect
                      x="0"
                      y="0"
                      height="100%"
                      width="100%"
                      fill="transparent"
                      stroke="navy" />
                    <rect
                      x="0"
                      y="0"
                      height="100%"
                      width={item.rating * 10}
                      fill="navy"
                      stroke="navy" />
                  </svg>
                  {item.rating}
                </span>
              </div>
            {/each}
          </div>
        </div>
      {/each}
    </div>
  </div>
</Panel>
