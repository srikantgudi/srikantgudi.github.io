<script>
  import {data} from './data/data';
</script>

<div class="section-title">
  WORK HISTORY
</div>
<div>
  <div class="work-hist">
    {#each data.exp as exp, idx}
      <div class="exp">
        <div class="job-title">
          <div>{exp.jobTitle}</div>
          <div>&raquo; {exp.dates}</div>
        </div>
        <div class="org-name">
          {exp.org}
        </div>
        <div class="technologies">
          Technologies used: {exp.technology}
        </div>
      </div>
    {/each}
  </div>
</div>