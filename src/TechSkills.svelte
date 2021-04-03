<script>
  import Rating from './Rating.svelte';
  import {data} from './data/data';
</script>

<div class="panel">
  <div class="panel-title">
    TECHNICAL SKILLS
  </div>
  <div class="panel-content">
    <div class="skills">
      {#each data.skills.primary as skill}
        <div class="skill primary">
          {skill.name}
        </div>
      {/each}
    </div>
    <div class="skills">
      {#each data.skills.secondary as skill}
        <div class="skill secondary">
          {skill.name}
        </div>
      {/each}
    </div>
  </div>
</div>