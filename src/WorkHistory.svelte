<script>
  import {data} from './data/data';
</script>
<div class="panel">
  <div class="title panel-title section lite">
    Work Experience
  </div>
  <div class="work-exp panel-content">
    {#each data.exp as xp}
      <div class="content-item">
        <div class="job-dates">
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