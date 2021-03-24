<script>
  import {data} from './data/data';
</script>

<style>
  
  @media screen and (max-width: 639px) {
    .details {
      font-size: 14px;
    }
    .exp {
      margin: 10px;
    }
    .job-title {
      font-size: 14px;
    }
  }
</style>

<div class="resume-section">
  {#each data.exp as exp, idx}
    <div class="exp">
      <div class="job-title">
        {exp.jobTitle}
        <div class="exp-period">{exp.dates}</div>
      </div>
      <div class="org-name">
        {exp.org}
      </div>
      <div class="details">
        <ul>
          {#each exp.content as text}
            <li>{text}</li>
          {/each}
        </ul>
      </div>
    </div>
  {/each}
</div>