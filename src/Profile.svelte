<script>
  import {data} from './data/data';
</script>
<div class="panel">
  <div class="title panel-title section lite">
    Profile
  </div>
  <div class="panel-content">
    {#each data.profile as text}
    <div class="content-item profile-item">
      {text}
    </div>
    {/each}
  </div>
</div>