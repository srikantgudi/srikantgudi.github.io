<script>
  import { Card, CardTitle, CardSubtitle, CardText, ListItem } from 'svelte-materialify';
  import {data} from './data/data';
</script>
<Card class="card">
  <CardTitle class="card-title">
    Profile
  </CardTitle>

  <CardText class="card-details">
    {#each data.profile as text}
      <div class="li content-text">
        {text}
      </div>
    {/each}
  </CardText>
</Card>
