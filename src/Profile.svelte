<script>
  import {data} from './data/data';
</script>
<div class="section-title">
  PROFILE
</div>
<div class="section-content">
  {#each data.profile as text}
  <div>
    {text}
  </div>
  {/each}
</div>
