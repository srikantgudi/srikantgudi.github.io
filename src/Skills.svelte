<script>
  import {data} from './data/data';
</script>

<style>
  .skills {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 0 10px;
    height: auto;
    margin: 1vh 4vw;
  }
  .skillgroup {
    min-width: 30%;
    box-shadow: 0 2px 2px #666666;
    margin-bottom: 1vmax;
    border-radius: 10px 10px 0 0;
    padding: 1vh 0;
  }
  .groupname {
    box-shadow: 0 0 4px #999999;
    background: #495057;
    color: whitesmoke;
    padding: 1vh 2vw;
    font-size: 16px;
    font-family: Montserrat;
    border-radius: 0 0 4px 4px;
  }
  .skillname {
    font-family: Montserrat;
    font-size: 14px;
    padding-left: 2vw;
    line-height: 1.5;
  }
  .skillname::before {
    content: '\bb\20';
  }
  @media screen and (max-width: 420px) {
    .skills {
      grid-template-columns: 1fr;
    }
  }
</style>

<div class="resume-section">
  <div class="sectiontitle">TECHNICAL SKILLS</div>
  <div class="skills">
    {#each data.skills as skill}
      <div class="skillgroup">
        <div class="groupname">
          {skill.group}
        </div>
        {#each skill.items as skillname}
          <div class="skillname">{skillname}</div>
        {/each}
      </div>
    {/each}
  </div>
</div>
