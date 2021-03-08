<script>
  import {mainOpt} from './store';
  import Panel from './Panel.svelte';
  
</script>

<Panel showcontent={$mainOpt === 'qual'}>
  <div slot="title" on:click={() => {$mainOpt='qual'}}>Academic Qualifications:</div>
  <div slot="content">
    <ul>
      <li>Master in Computer Management</li>
      <li>Bachelor of Commerce</li>
    </ul>
  </div>
</Panel>
