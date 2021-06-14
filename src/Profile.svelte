<script>
  import { Card, CardTitle, CardSubtitle, CardText, ListItem } from 'svelte-materialify';
  import {data} from './data/data';
  import {currentComp} from './store.js';

  const setComp = (n) => {
    console.log('comp:',n)
    $currentComp = n
  }
</script>

<Card class="card">
  <div on:click={() => setComp(1)}>
    <CardTitle class="card-title">
      Profile 
    </CardTitle>
  </div>

  <div class="card-details" class:active={$currentComp === 1}>
    <CardText>
      {#each data.profile as text}
        <div class="li content-text">
          {text}
        </div>
      {/each}
    </CardText>
  </div>
</Card>
