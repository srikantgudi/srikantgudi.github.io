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
			<div class="title groupname arialrounded">
        {grouptitle.toUpperCase()}
      </div>
			<div class="skills">
				{#each data.skills[grouptitle] as skill}
          <div class="content-item">
            <div class="ubuntu skill-name">
              <div>
                <Rating width="400" txt={skill.name} bg='grey' r={skill.rating} />
              </div>
            </div>
          </div>
				{/each}
			</div>
		{/each}
  </div>
</div>