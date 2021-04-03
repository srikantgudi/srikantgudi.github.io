<script>
  import {data} from './data/data';
</script>
<div class="panel">
  <div class="panel-title">
    WORK EXPERIENCE
  </div>
  <div class="work-exp">
    {#each data.exp as xp}
      <div class="exp">
        <div>
          {xp.dates}
        </div>
        <div class="job-title">
          {xp.jobTitle}
        </div>
        <div>
          {xp.org}
        </div>
      </div>
    {/each}
  </div>
</div>