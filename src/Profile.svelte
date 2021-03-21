<script>
  import {data} from './data/data';
</script>
<div>
  <div class="sectiontitle">About me</div>
  <div class="content-text">
    <ul>
      {#each data.profile as text}
      <li>
        {text}
      </li>
      {/each}
    </ul>
    <div class="sectiontitle">Academic</div>
    <div>
      <ul>
        <li>Master in Computer Management</li>
        <li>Bachelor of Commerce</li>
      </ul>
    </div>
  </div>
</div>
