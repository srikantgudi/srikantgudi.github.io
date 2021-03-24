<script>
  import {data} from './data/data';
  import SkillLevel from './SkillLevel.svelte'

  let skills = data.skills;
</script>

<style>
  .skills {
    margin: 1vh 4vw;
    overflow-y: auto;
  }
  .skillgroup {
    min-width: 30%;
    box-shadow: 0 2px 2px #666666;
    margin-bottom: 1vmax;
    border-radius: 30px 10px 30px 0;
    padding: 1vh 0;
  }
  .groupname {
    box-shadow: 0 0 4px #999999;
    background: #495057;
    color: whitesmoke;
    padding: 1vh 2vw;
    font-size: 16px;
    font-family: Montserrat;
    border-radius: 10px 0 4px 4px;
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
</style>

<div class="resume-section">
  <div>
    {#each Object.keys(skills) as skill}
      <SkillLevel text={skill} level={skills[skill]} />
    {/each}
  </div>
</div>
