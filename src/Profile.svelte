<script>
  import {data} from './data/data';
</script>
<div class="panel">
  <div class="panel-title">
    PROFILE
  </div>
  <div class="panel-content">
    {#each data.profile as text}
    <div class="content-item">
      {text}
    </div>
    {/each}
  </div>
</div>