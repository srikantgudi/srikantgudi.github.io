<script>
  import {data} from './data/data';
</script>
<div class="section-title">
  PROFILE
</div>
<div class="section-content">
  <div class="profile-content">
    {#each data.profile as text}
    <div>
      <div class="profile-li">
        {text}
      </div>
    </div>
    {/each}
  </div>
</div>
