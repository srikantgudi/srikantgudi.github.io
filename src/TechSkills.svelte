<script>
  import {data} from './data/data';
  import Rating from './Rating.svelte';
</script>

<div class="panel">
  <div class="panel-title">
    TECHNICAL SKILLS
  </div>
  <div class="panel-content">
    {#each Object.keys(data.skills) as grouptitle}
			<div class="title groupname grey arialrounded">{grouptitle.toUpperCase()}</div>
			<div class="skills">
				{#each data.skills[grouptitle] as skill}
				<div class="skill">
					<div class="ubuntu skill-name">
            <div>
              <Rating text={skill.name} rating={skill.rating} />
            </div>
					</div>
				</div>
				{/each}
			</div>
		{/each}
  </div>
</div>