<script>
  import {data} from './data/data';
</script>
<div class="panel">
  <div class="title panel-title section lite">
    Work Experience
  </div>
  <div class="work-exp panel-content">
    {#each data.exp as xp}
      <div class="content-item exp">
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
          <div>
            Technologies used: <span class="technology">{xp.technology}</span>
          </div>
          <div class="job-details">
            <details>
              <summary>Details:</summary>
              <ul>
                {#each xp.content as xptxt}
                  <li>{xptxt}</li>
                {/each}
              </ul>
            </details>
          </div>
        </div>
      </div>
    {/each}
  </div>
</div>