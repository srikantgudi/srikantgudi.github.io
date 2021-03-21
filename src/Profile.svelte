<script>
  import {data} from './data/data';
</script>
<div class="resume-section">
  <div class="sectiontitle">PROFILE</div>
  <div class="subsection">
    <div class="subsectiontitle">About me</div>
    <div class="content-text">
      <ul>
        {#each data.profile as text}
        <li>
          {text}
        </li>
        {/each}
      </ul>
    </div>
  </div>
  <div class="subsection">
    <div class="subsectiontitle">Academic</div>
    <div class="content-text">
      <ul>
        <li>Master in Computer Management</li>
        <li>Bachelor of Commerce</li>
      </ul>
    </div>
  </div>
</div>
