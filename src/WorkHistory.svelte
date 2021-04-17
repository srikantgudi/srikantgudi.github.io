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
        <div class="exp-detail">
          <div>
            {xp.org}
          </div>
          <div class="technology">
            {xp.technology}
          </div>
        </div>
      </div>
    {/each}
  </div>
</div>