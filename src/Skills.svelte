<script>
  import {data} from './data/data';
</script>

<style>
  
  @media screen and (max-width: 640px) {
    .skillgroup {
      margin: 0;
      width: 100%;
    }
  }
</style>

<div class="section-title">
  TECHNICAL SKILLS
</div>
<div class="section-content">
  <div class="skills">
    {#each data.skills as skill}
      <div class="skillname">
        {skill}
      </div>
    {/each}
  </div>
</div>
