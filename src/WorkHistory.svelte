<script>
  import {data} from './data/data';
</script>

<style>
  .org-name, .exp-period {
    font-size: 14px;
  }
  .job-title {
    font-family: Montserrat;
    background-color: #495057;
    color: #f8f9fa;
    padding: 1vh 2vw;
    margin: 0;
  }
  .org-name {
    font-family: Montserrat;
    box-shadow: 0 0 4px #495057;
    padding: 1vh 2vw;
  }

  .exp {
    display: flex;
    flex-flow: column;
    height: auto;
    margin: 1vh 4vw;
    box-shadow: 0 2px 2px #999999;
  }
  .details {
    margin: 1vh 4vw;
    font-family: Montserrat;
    font-size: 16px;
  }
  .exp:hover {
    box-shadow: 0 0 10px #666666;
    font-size: 110%;
    transition: all 1s;
    background-color: lightcyan;
    border-radius: 30px;
  }
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