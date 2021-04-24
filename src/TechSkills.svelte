<script>
  import {data} from './data/data';
  import Rating from './Rating.svelte';
</script>

<div class="panel">
  <div class="title panel-title section lite">
    Technical Skills
  </div>

  <div class="panel-content">
    {#each Object.keys(data.skills) as grouptitle}
      <div class="skill-group">
        <div class="title groupname">
          {grouptitle.toUpperCase()}
        </div>
        <div class="skills">
          {#each data.skills[grouptitle] as skill}
            <div class="skill">
              <Rating width="200" txt={skill.name} bg='grey' r={skill.rating} />
            </div>
          {/each}
        </div>
      </div>
		{/each}
  </div>
</div>
