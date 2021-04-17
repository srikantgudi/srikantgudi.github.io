<script>
  import {data} from './data/data';
  import Rating from './Rating.svelte';
</script>

<div class="panel">
  <div class="panel-title">
    TECHNICAL SKILLS
  </div>
  <div class="panel-content">
    <h3>PRIMARY</h3>
    <div class="skills">
      {#each data.skills.primary as skill}
      <div class="skill primary">
        <div>
          <Rating text={skill.name} rating={skill.rating} />
        </div>
      </div>
      {/each}
    </div>
    <h3>Secondary</h3>
    <div class="skills">
      {#each data.skills.secondary as skill}
        <div class="skill secondary">
          <div>
            <Rating text={skill.name} rating={skill.rating} />
          </div>
        </div>
      {/each}
    </div>
  </div>
</div>